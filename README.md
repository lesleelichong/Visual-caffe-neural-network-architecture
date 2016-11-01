# win平台可视化Caffe网络结构
Caffe自带Python目录里包含一个draw_net.py文件，可以**可视化神经网络结构**。在windows上运行这个Python程序，需要安装Caffe的Python模块、安装Python版本的Protobuf，以及Python的pydot模块。
#### Caffe的Python模块安装
作者直接从Github上下载 [微软移植的Caffe](https://github.com/BVLC/caffe/tree/windows),然后在windows目录里将CommonSettings.props.example文件改为CommonSettings.props文件，打开Caffe.sln工程，修改文件里的参数设置，注意里面关于Python编译的参数配置，然后生成解决方案，编译成功后在**Build\x64\Release\pycaffe**目录里找到**caffe**模块，将该模块放入**Python27\Lib\site-packages**目录里。
#### Google的Protobuf安装
参照网上教程安装，或者直接将作者编译好的protobuf文件夹里的三个文件protobuf-2.6.1-py2.7-nspkg.pth、protobuf-2.6.1.dist-info、google复制到**Python27\Lib\site-packages**目录里即可。
#### Pydot模块安装
首先，下载graphviz-2.38.msi文件并且安装它，将Graphviz2.38\bin的目录设置到系统环境变量里；其次，下载pyparsing-1.5.7.win32-py2.7.exe
并且将其安装到**Python27\Lib\site-packages**目录里；最后，下载pydot-1.2.3包文件，cmd方式进入该目录，执行python setup.py install 即可。
#### 运行draw_net.py
打开PowerShell(用cmd方式也可以)，执行python draw_net.py resnet50.txt resnet50.png，就会生成resnet50.png的可视化图。(不在同一目录自己添加文件自己所在的目录)