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
	cd - 跳转到上一次所在的路径
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
	    eg:cat 1.txt 2.txt > 3.txt

grep :从指定的文件中搜索需要的内容

	
