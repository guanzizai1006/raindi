# 电脑文件目录总结
> 时间    : 20190819 20:00
> author  : Bruce <2873102747@qq.com>

## 1. Qt完成图像界面
  本地地址： '/home/bruce/QtProjects/testBruce004/test004'
  参考资料： 
  ***
  功能需求：
  
> **控制区：**
>> 1  开始拍摄 -> （无子按钮：唯一的功能：开始录像+进行默认选定区域图像进行实时检测(根据“检测物品种类”的默认值的方式） 
2 系统设置 -> （ 有子按钮：图像的分辨率 + 亮度 + 对比度 + gamma值 ）
3 学习模板 -> （ 无子按钮，功能：完成选定区域图像的图像处理，至于是提取关键点、或者测出样品的长度 ）
4 退出处理 -> (无子按钮： 关闭线程，关闭摄像，不退出程序)
5 阈值设定 -> （直接更改数字，程序读取这个变量）
6 工作模式选择(下拉框) -> （有子按钮：检测相似度 + 检测长度 ，用switch跳转）

> **显示区：**
>> 视频区：显示实时视频
模板区 ：显示选定区域图像
OK：     输出OK/NG两种状态
视频帧数：
实时匹配度：
前一个匹配度：
每分钟良品数：
总时长良品数：

> 待添加的功能：两种模式：1.原图(原图模式，用户可以手动调整小框区域，)；2.边缘(边缘模式，其在学习过程中，自动去学习边缘)
TODO：当开启摄像头时，即完成区域框框图像的显示，并将此区域送去图像检测；当完成设定开始工作了，就完成屏幕的锁定，禁止用户操作


## 其他注意事项：
> 1. TODO：【这里配置的是ubuntu16.04自带的opencv2.4版本，因为版本太低，所以其**caputer.get(5)**会return -1,升级到opencv3.2版本及以上就会解决了】
     <https://github.com/opencv/opencv/issues/4355>
> 2. 关于**界面选取任意部分，描出框框，可参考如下代码：首先，完成ROI区域的提取，**
     参考教程：<https://blog.csdn.net/qq_38441692/article/details/98770948>
     代码地址：<https://github.com/chengyangkj/VideoRoi>
> 3. 实现如下功能“b 工作模式选择”添加“a. 测长度；b. 测形状；c. 测颜色”等等
     <https://blog.csdn.net/mars_xiaolei/article/details/88392364>
     于是，mainwindow.cpp中 ,可以完成 设置“工作模式”下拉框的更新。  
> 4. 当电脑重启或者插拔USB摄像头，可能会出现摄像头ID更换了的情况， 
     终端输入 (base) bruce@zhengdz-PowerEdge-T310:~$ ls /dev/vide* 
     即可查看到id号，'/dev/video0'  便于代码中进行修改capture(0) //0为此时的摄像头id。
   
  
  
  # 2. opencv基本处理函数、深度学习相关demo及论文
  
  >      **/home/bruce/project_bruce/** 和 
      **/home/bruce/Downloads/git** 
    地址下有部分深度学习边缘检测的demo,
    其中 子文件夹 **/python_bruce** 是二维码检测部分内容。
    
  
  # 3. 本机的虚拟环境目录（分别配置安装了tensorflow、tensorflow等，caffe也配置了）
  > 1. 输入命令 'conda env list',可以查看当前所有路径
    2. 输入命令 'conda activate py36',即可完成环境切换
    3. 输入命令 'conda env export > py36.yaml ' 即可完成通过conda安装的环境
    4. 输入命令 'pip freeze > py36.txt ',即可导出通过pip安装的环境
    5. 输入命令 'conda deactivate' 即可退出当前虚拟环境，回到第二步
    6. 输入命令完成另外一台机器的环境安装。conda env create -f py36.yaml 和 pip install -r py36.txt 完成安装。
    
    
> 已安装的虚拟环境目录如下：
>> #
base                  *  /home/bruce/anaconda3
flyai_ChestXray          /home/bruce/anaconda3/envs/flyai_ChestXray
py36                     /home/bruce/anaconda3/envs/py36
py36_pytorch             /home/bruce/anaconda3/envs/py36_pytorch
py36_yolo_tiny           /home/bruce/anaconda3/envs/py36_yolo_tiny
py_caffe_hed             /home/bruce/anaconda3/envs/py_caffe_hed

  
  
  
  
  
  
  
  
  


