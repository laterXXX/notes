安装Aria2:

sudo add-apt-repository ppa:t-tujikawa/ppa
sudo apt-get update
sudo apt-get install aria2

sudo mkdir /etc/aria2    #新建文件夹  
sudo touch /etc/aria2/aria2.session    #新建session文件
sudo chmod 777 /etc/aria2/aria2.session    #设置aria2.session可写
sudo apt-get install mousepad
sudo mousepad /etc/aria2/aria2.conf    #创建配置文件

配置文件内容：

#＝＝＝＝＝＝＝＝＝文件保存目录自行修改
dir=/home/username/Desktop/Downloads #username根据实际情况修改
disable-ipv6=true

#打开rpc的目的是为了给web管理端用
enable-rpc=true
rpc-allow-origin-all=true
rpc-listen-all=true
#rpc-listen-port=6800
#断点续传
continue=true
input-file=/etc/aria2/aria2.session
save-session=/etc/aria2/aria2.session

#最大同时下载任务数
max-concurrent-downloads=5

save-session-interval=120

# Http/FTP 相关
connect-timeout=120
#lowest-speed-limit=10K
#同服务器连接数
max-connection-per-server=10
#max-file-not-found=2
#最小文件分片大小, 下载线程数上限取决于能分出多少片, 对于小文件重要
min-split-size=10M
#单文件最大线程数, 路由建议值: 5
split=10
check-certificate=false
#http-no-cache=true


baiduexporter
Tampermonkey



sudo aria2c --conf-path=/etc/aria2/aria2.conf



http://aria2c.com/ 