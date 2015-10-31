* 支持推送给它的rtmp流的接收与播放器请求的分发；
* rtmp流媒体服务器树状网络集群的构建；
* 支持iPhone，Android。

##如何获取CrtmpServer
* 官网下载(http://www.rtmpd.com/)
* 最新版本可以从SVN获取：
svn co --username anonymous https://svn.rtmpd.com/crtmpserver/trunk

## crtmpserver编译安装
###### 编译环境要求:
* GCC and other C++ tools
* SVN
* libdl, libssl, libcrypto

确保你有devel包的libdl,ssl和crypto，在编译之前安装,查看已安装的某个软件rpm -qa |grep 包名，如果你安装了openssl包的话会包括libssl, libcrypto

###### 安装cmake
下载最新的cmake(http://www.cmake.org/)
```Shell
    #tar -zxvf cmake-2.8.7.tar.gz  
    #cd cmake-2.8.7  
    #./bootstrap  
    #gmake  
    #make install  
```
###### 编译安装步骤
```Shell
#cd crtmpserver/builders/cmake
#cmake .
```
这一步骤将创建所有的makefile的所需。如果有包丢失，CMake会警告
```Shell
#make
```
汇编程序会在在几分钟内完成。在编译安装完成后，你可以使用下面的命令测试：
```Shell
./crtmpserver/crtmpserver crtmpserver/crtmpserver.lua
```
如果一切顺利,crtmpserver会显示ip,端口,协议和应用名称列表

###### 测试
接下来我们测试一下服务器。遵循这些简单的步骤：

* 下载一个简单的FLV或MP4文件。你可以从这里下载一个文件：
http://www.mediacollege.com/adobe/flash/video/tutorial/example-flv.html

把你下载的文件放到crtmpserver/media文件夹

* 下载一个Flv播放器，从这里下载
http://www.longtailvideo.com/players/jw-flv-player
```Html
<html>
<head>
<script src="1.js"></script>
<script src="jwplayer.js"></script>
</head>
<body>
<div id='myplayer'></div> <script type='text/javascript'>    
 jwplayer('myplayer').setup({       
 file: '20051210-w50s.flv',       
 width: '640',        
 height: '480'     }); 
</script>
</body>
</html>
```



