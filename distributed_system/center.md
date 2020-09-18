# center
    1.设备服务器
        接收连接请求，身份校验
        分配空闲集群服务器
        处理接收信息
    2.集群服务器
    3.公司
        使用TCP/IP协议进行通信
        
        
## HttpManager
```x
size_t receive_data(void *contents, size_t size, size_t nmemb, void *stream)//append string后面加字符,并返回数据大小
```
```x
size_t writedata2file(void *ptr, size_t size, size_t nmemb, FILE *stream)//向文件中写入数据
```
```x
size_t readData(void* buffer,size_t size, size_t nmemb, void* userdata)//读取数据,buffer为接收到的数据，size＊nmemb为接收的数据大小，userdata返回的数据指定的输出流
```
```x
 static size_t OnWriteData(void* buffer, size_t size, size_t nmemb, void* userdata)
```
```x
static int writer(char *data, size_t size, size_t nmemb, std::string *buffer_in)//将数据连接到buffer中
```
```x
 bool HttpManager::post(const std::string & info, const std::string &method//Http协议相关，用到libcurl（网络协议库）设置curl_easy_setopt 参数
```
## main.cpp
```x
void showState();//显示工作状态，名称，当前终端数目，数据量
```
```x
main函数，调用以下
	while (systemRunBlog)
	{
	boost::thread_group mainThreadGroup;    //建立线程组
	mainThreadGroup.create_thread(master_to_equipment_main);
	mainThreadGroup.create_thread(master_to_workstation_main);
	mainThreadGroup.create_thread(uploadInfoToCampany);//上传公司服务器线程
	mainThreadGroup.create_thread(showState);//小车控制线程  mty20190417
    mainThreadGroup.join_all();
```
## main.hpp
    自定义变量、函数
## master_to_company.cpp
中央服务器->公司
```x
void uploadInfoToCampany()//上传信息到公司服务器
std::vector<std::string> infoToCampany_temp;//一个封装了动态数组的顺序容器
writeLock workstastionInfoListWrite(infoToCompany_mutex); //加锁，防止同时操作
之后导入配置文件，主机名，主机地址，端口，协议
```
```x
string savePigInfo(vector<string> &parameters)//保存猪信息（体重，背膘，quality）
写入日志，返回200或400
```
## master_to_company.hpp
```x
void uploadInfoToCampany();//向公司上传信息
string savePigInfo(vector<string> &parameters);//保存猪信息
```
## master_to_equipment.cpp
中央服务器->设备客户端
```x
std::vector<equipment_client_ptr> equipmentClientList;//设备客户端保存在vector中
```
```x
class talk_to_equipment_client : public
boost::enable_shared_from_this<talk_to_equipment_client>//与设备通信的类
public:
void start()//启动，上锁，读取设备信息
void stop()//关闭，解锁
private:
处理信息，并回复
void on_read(const error_code & err, size_t bytes)//正常状态->workstationInfo recvInfo sendInfo 三选一，否则打印 无效信息
void on_sendWorkstationInfo(std::string &equipment_name)//向工作站传送信息
void on_ping()
void do_ping()
void do_ask_clients()
void on_write(const error_code & err, size_t bytes)
void do_read()
void do_write(const std::string & msg)
size_t read_complete(const boost::system::error_code & err, size_t bytes)
void on_check_ping(unsigned long time)//检查ping
```
```x
void handle_accept(talk_to_equipment_client::ptr client, const boost::system::error_code & err)//处理接收，启动新连接
```
```x
std::string loadBalance(std::string &equipment_name)//负载均衡，找到正大设备，并寻找空闲工作站
```
```x
int master_to_equipment_main()//主要函数，连接客户端的服务器程序启动，boost
```
## master_to_workstation.cpp
中央服务器->计算工作站
```x
端口8802
服务运行数字2
int insertWorkstationInfoList(std::string name, std::string stringRecv);//将信息插入到接收到工作站信息列表中
int addWorkstationList(const workstationInfo &workstation_info);//将工作站信息添加到工作站列表中
int updateWorkstationList(std::string name, std::string stringRecv);//更新工作站列表中的信息
void initWorkstationList();//测试使用
class talk_to_workstation_client //参考master_to_equipment.cpp
static ptr new_()//与client 与workstations对话
```
```x
void on_login(const std::string & msg)//获取登录信息
```
```x
void on_recvInitInfo(const std::string & msg)//登录检测
```
```x
void on_recvStateInfo(const std::string & msg)//获得状态信息
```
|    normal     |           ^_^           |
| ------------- | ----------------------- |
| recvStateInfo | recvLargeBufferOk/error |
```x
void on_recvInfoFromWorkstation(const std::string & msg)//从工作站接收信息,同样判断normal,ping
```
```x
void start_recv_info_to_company()//开始接收公司信息
```
```x
void do_recv_info_to_company(const error_code & err, size_t bytes)//接收公司信息
```
## Rrconfig.cpp
```x
bool RrConfig::IsSpace(char c)//判断空格
bool RrConfig::IsCommentChar(char c)//判断字符#
void RrConfig::Trim(std::string & str)//删除空格
bool RrConfig::AnalyseLine(const std::string & line, std::string& section, std::string & key, std::string & value)//判断xxx是否为空
bool RrConfig::ReadConfig(const std::string & filename)//读取配置文件
之后 读取string，int，float数据的函数
```
## tools.cpp
```x
string getNowTime()//获取当前时间
vector<uchar> encodePNG(cv::Mat matInput)//储存PNG图像
string get_date()//获取日期
```























