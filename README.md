# Linux_basic
绝对路径：cd /home/python
相对路径：cd Downloads

. 表示：当前那路径

	..表示：当前路径的上一层

	../.. 表示：当前路径的上二层

没有...或者以上的

ls:
	ls 查看当前路径下的文件以及文件夹的名字
	
	ls /bin 表示：查看根目录下的bin文件夹下的东西
	
	ls Documents 表示：查看当前路径下的Documents文件夹下的所有东西

	
	ls *:  	* 表示任意多个字符，也可以没有

			
		? 表示一个字符，一定有1个，不能没有

 eg: ls *.t?t				
		[xn] 表示：中括号中的任意一个字符
	eg: ls *.t[xn]t		
		[abcdef]可以写成[a-f]:表示 从a到f之间的任意一个字符

	
	-a 隐藏文件
	-l 列表显示风格
	-h 配合-l 显示一个合理的大小单位  ls -l -h

cd ：
	cd Desktop 进入到Desktop这个文件夹
	
	cd 文件夹的名字
	cd .. 跳转到当前路径的上一层	
	cd - 跳转到上一次所在的路径（类似电视机遥控器中的回看）	
	cd ~ 跳转到当前用户的家目录(/home/python)

pwd：显示当前操作的路径（绝对路径   /aaa/bb/cc）

clear:清屏

tab键：用来自动补全

touch:创建一个文件，linux中没有后缀的说法，所有文件名自定义

重定向:

	ls -ahl > test.txt 表示：把本来显示在终端上的信息写入到test.txt文件中
	
			>> 和 > 的区别是:>> 是在源文件的末尾添加，而> 先清空然后再添加
			
gedit haha.txt 用gedit编辑器打开haha.txt文件

more:

	more test.txt 如果test.txt文件的内容如果很多，那么就用分屏的方式显示

	
ls -alh | more 先把ls -alh显示的内容存放到 管道|中，然后more从管道中去数据，然后分屏显示

mkdir:创建文件夹
	
	mkdir a 在当前路径下创建a文件夹	
	mkdir A/B/C 不能创建，需要添加-p          eg: mkdir A/B/C -p
     
tree：以目录树的方式显示 文件夹结构

rmdir: 删除空文件夹

rm:
	
	rm haha.txt 删除一个普通文件	
	rm 文件夹 会有提示，要删除的东西是个文件夹，，如果真的要删除可以添加 -r(递归删除文件夹里面的所有东西)

ln -s [源文件] [链接文件] 表示：软连接

ln [源文件] [链接文件] 表示：硬链接，，，注意硬链接数量为1时，才会真正删除数据，否则不会

	eg:    !ln -s  /content/val2014   /content/drive/MyObjectDetection1/MyObjectDetection1/datasets/coco

cat 	1. 查看文件的内容
	
	2. 合并多个文件  需要和  重定向>配合	
	cat 1.txt 2.txt > 3.txt
grep :从指定的文件中搜索需要的内容

	
	-n:显示行号	
	-i:不区分大小写
	-v:取反，即不包含需要的内容的行
	
	^a	行首,搜寻以 m 开头的行；grep -n '^a' 1.txt
	ke$	行尾,搜寻以 ke 结束的行；grep -n 'ke$' 1.txt
	[Ss]igna[Ll]	匹配 [] 里中一系列字符中的一个；搜寻匹配单词signal、signaL、Signal、SignaL的行；
			eg:  grep -n 	'[Ss]igna[Ll]' 1.txt
	.	(点)匹配一个非换行符的字符；匹配 e 和 e 之间有任意一个字符，可以匹配 eee，eae，eve，但是不匹配 ee，eaae；
		grep -n 'e.e' 1.txt

查找文件：
find 路径 -name '*.t?t'

	通配符，注意点：
	[a-zA-Z0-9]*.txt
			find ./ -name test.sh	查找当前目录下所有名为test.sh的文件
			find ./ -name '*.sh'		查找当前目录下所有后缀为.sh的文件
			find ./ -name "[A-Z]*"	查找当前目录下所有以大写字母开头的文件
			find /tmp -size 2M		查找在/tmp 目录下等于2M的文件
			find /tmp -size +2M	查找在/tmp 目录下大于2M的文件
			find /tmp -size -2M	查找在/tmp 目录下小于2M的文件
			find ./ -size +4k -size -5M	查找当前目录下大于4k，小于5M的文件
			find ./ -perm 0777		查找当前目录下权限为 777 的文件或目录

复制文件：

cp a b 将a文件夹整体复制到b文件夹下
	
cp a/* b 将a文件夹下的所有内容赋值到b文件夹下
	-a	该选项通常在复制目录时使用，它保留链接、文件属性，并递归地复制目录，简单而言，保持文件原有属性。
	-f	已经存在的目标文件而不提示
	-i	交互式复制，在覆盖目标文件之前将给出提示要求用户确认
	-r	若给出的源文件是目录文件，则cp将递归复制该目录下的所有子目录和文件，目标文件必须为一个目录名。
	-v	显示拷贝进度



剪切文件：
	
mv a b 将a文件夹整体移动（剪切）到b文件夹下


tar -cvf xxx.tar * 打包
gzip xxx.tar 压缩
gzip -d xxx.tar.gz解压
tar -xvf xxx.tar解包


常见的压缩解压方式：
	tar -zcvf xxx.tar.gz *
	tar -zxvf xxx.tar.gz

	tar -jcvf xxx.tar.bz2 *
	tar -jxvf xxx.tar.bz2

压缩文件：zip [-r] 目标文件(没有扩展名) 源文件
解压文件：unzip -d 解压后目录文件 压缩文件

linux：多用户多任务的OS

ifconfig :查看ip地址
	
WINDOWS中使用ipconfig

ping：

	ping 192.168.17.76 测试网络连接是否正常

ssh:远程登录

ssh python@192.168.17.76
	
ssh 用户名@ip

whoami：查看当前用户名

who:查看当前登录的用户信息

exit:
	如果是图形界面，退出当前终端；
	如果是使用ssh远程登录，退出登陆账户；
	如果是切换后的登陆用户，退出则返回上一个登陆账号

Ctrl+a快速跳到行头
Ctrl+e快速跳到行尾

useradd [新的用户名] -m -d /home/新用户名 -g 组名

passwd [用户名]

su [需要切换的用户名]
su - [需要切换的用户名]    切换用户后，还会主动跳转到该用户的家目录

python---->laowang----->python

sudo 

当需要超级管理员的权限时需要添加，并且在命令行的最前面，后面需要空格
sudo passwd laowang

sudo -s 直接切换到root用户

groupadd YYY 添加一个YYY用户组

groupdel YYY 删除一个组，注意需要sudo

cat /etc/group

groups laowang表示：查看laowang所属的所有用户组

usermod -g YYY laowang 把老王添加到YYY组里面

usermod -a -G XXX laowang 把老王添加到XXX组里面

	
	-g 和 -G，-g指定的是默认的组

useradd创建的新用户没有sudo，或者切换到root的权限，需要把这个用户添加到adm、sudo组里面才可以

chmod 修改文件的权限

	
	u：拥有者	
	g:同组者	
	o：其他人	
	a:所有，即u、g、o
	
	+ 添加权限	
	- 去除权限	
	= 设定权限
	
	r:读------>对应的数字是4
	w：写------>对应的数字是2
	x：执行------>对应的数字是1
	eg: chmod 761 1.py  ---->  -rwxrw---x 1 hzy hzy 0 Aug  9 14:01 1.py

chmod 777 文件夹，只会修改文件夹的权限为777 ，不会修改里面文件的权限
	
	-R 会修改文件夹里面所有的文件、文件夹的权限（递归）
ssh

A.安装ssh服务器
	
	sudo apt-get install openssh-server
B.远程登陆

	ssh 用户名@IP
使用ssh访问，如访问出现错误。可查看是否有该文件 ～/.ssh/known_ssh 尝试删除该文件解决。	

远程拷贝文件,scp -r 的常用方法：

1.使用该命令的前提条件要求目标主机已经成功安装openssh-server

	如没有安装使用 sudo apt-get install openssh-server 来安装
2.使用格式：

	scp -r 目标用户名@目标主机IP地址：/目标文件的绝对路径  /保存到本机的绝对/相对路径

举例：
	scp -r hzy@192.168.1.100:/home/QQ_dir/ ./mytest/lisi

在后续会提示输入“yes”此时，只能输“yes”而不能简单输入“Y”
拷贝单个文件可以不加 -r参数，拷贝目录必须要加。

本地文件复制到远程：

	scp FileName RemoteUserName@RemoteHostIp:RemoteFile
	scp FileName RemoteHostIp:RemoteFolder
	scp FileName RemoteHostIp:RemoteFile
本地目录复制到远程：

	scp -r FolderName RemoteUserName@RemoteHostIp:RemoteFolder
	scp -r FolderName RemoteHostIp:RemoteFolder
远程文件复制到本地：

	scp RemoteUserName@RemoteHostIp:RemoteFile FileName
	scp RemoteHostIp:RemoteFolder FileName
	scp RemoteHostIp:RemoteFile FileName
远程目录复制到本地：

	scp -r RemoteUserName@RemoteHostIp:RemoteFolder FolderName
	scp -r RemoteHostIp:RemoteFolder FolderName
