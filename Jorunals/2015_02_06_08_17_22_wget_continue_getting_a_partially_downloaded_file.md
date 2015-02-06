How to wget continue getting a partially-downloaded file
==============================================

### 断点续传
This is useful when you want to finish up a
download started by a previous instance of
Wget, or by another program.  For instance:

    wget -c/--continue
    wget -c http://balabala.ba/file_to_download


### 下载整个http或者ftp站点。

    wget http://balabala.ba

这个命令可以将http://balabala.ba 首页下载下来。
使用-x会强制建立服务器上一模一样的目录，
使用-nd参数，那么服务器上下载的所有内容都会加到本地当前目录。

### 利用代理服务器进行下载

用户的网络需要经过代理服务器，那么可以让wget通过代理服务器
进行文件的下载。此时需要在当前用户的目录下创建一个.wgetrc
文件。文件中可以设置代理服务器：

    http-proxy = xxx.xxx.xxx.xxx:8080
    ftp-proxy = xxx.xxx.xxx.xxx:8080

分别表示http的代理服务器和ftp的代理服务器。如果代理服务器需
要密码则使用：

    –proxy-user=USER设置代理用户
    –proxy-passwd=PASS设置代理密码

这两个参数。
使用参数–proxy=on/off 使用或者关闭代理。
wget还有很多有用的功能，需要用户去挖掘。


### 密码和认证

wget只能处理利用用户名/密码方式限制访问的网站，可以利用两个参数：

    –http-user=USER设置HTTP用户
    –http-passwd=PASS设置HTTP密码
对于需要证书做认证的网站，就只能利用其他下载工具了，例如curl。

### 选择性的下载

可以指定让wget只下载一类文件，或者不下载什么文件。

    wget -m –reject=jpg http://balabala.ba

表示下载，但是忽略jpg文件。

    –accept=LIST 可以接受的文件类型
    –reject=LIST拒绝接受的文件类型


Tested on OSX 10.9.2, wget version: GNU Wget 1.15 built on darwin13.1.0
