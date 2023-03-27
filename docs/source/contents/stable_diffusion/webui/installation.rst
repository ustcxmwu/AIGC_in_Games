.. _Stable Diffusion WebUI 安装:

Stable Diffusion WebUI 安装
================================================================================


Windows 安装 Stable-Diffusion WebUI
--------------------------------------------------------------------------------

环境准备
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. 安装git: 从 `Win Git 下载 <https://git-scm.com/download/win>`_ 下载并安装git软件；

.. code:: bash

    # 验证git安装
    (base) ➜  ~ git --version
    git version 2.38.0
    (base) ➜  ~


2. [可选] 安装 wget: 从 `Wget 下载链接 <https://eternallybored.org/misc/wget/>`_ 下载对应版本 wget.exe 文件并放置到路径
'C:/Windows/System32' 中；

.. code:: bash

    # 验证 wget 安装
    (base) ➜  ~ wget --version
    GNU Wget 1.21.3 在 darwin22.1.0 上编译。

3. 安装 Anaconda， 从 `Annconda 下载 <https://www.anaconda.com/products/distribution>`_ 页面上选择 Windows 版本的 Anaconda
下载并安装，安装完毕可以在命令行运行 python --version 命令进行验证

.. code:: bash

    ~# python --version
    Python 3.10.9



安装 Stable-Diffusion WEBUI
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. 从 github 上下载源代码

.. code:: bash

    ~ git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git
    
2. 切换到 standard-diffusion-webui 文件夹下，运行批处理文件 webui.bat
#. 打开 https://localhost:7860 页面展示 webui页面表示安装成功.

.. Attention:: 首次运行 webui.bat 会下载相应的模型和文件，如果运行不成功，可以多次运行 webui.bat 文件来进行修复.





Ubuntu (Unix/Linux) 安装 Stable-Diffusion WebUI
--------------------------------------------------------------------------------

环境准备
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. 安装 git， wget

.. code:: bash

    ~ apt install git
    # 验证git安装
    ~ git --version
    git version 2.38.0
    ~
    ~ apt install wget
    # 验证 wget 安装
    ~ wget --version
    GNU Wget 1.21.3 在 darwin22.1.0 上编译。

2. [可选] 安装会话管理工具 Tmux, Tmux 常用命令可查阅: `Tmux 常用命令 <https://zhuanlan.zhihu.com/p/90464490>`_.

.. code:: bash

    ~ apt install tmux

3. 安装 Anaconda，从 Anaconda 下载最新的安装脚本并运行, Anaconda 是包含了 Python 安装包，具体可参阅: `Anaconda 官网 <https://www.anaconda.com/>`_。

.. code:: bash

    ~ wget https://repo.anaconda.com/archive/Anaconda3-2023.03-Linux-x86_64.sh
    ~ chmod 755 Anaconda3-2023.03-Linux-x86_64.sh
    ~ ./Anaconda3-2023.03-Linux-x86_64.sh

安装完毕可进行 Python 安装环境验证

.. code:: bash

    ~# python --version
    Python 3.10.9
    

Stable-Diffusion WEBUI 安装
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. 从 Github 上下载 Stable-Diffusion WEBUI 代码

.. code:: bash

    git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git

2. 切换到 stable-diffusion-webui 文件夹下，修改 webui.sh 文件第59行 'can_run_as_root=1'
#. 运行命令 './webui.sh'，首次运行该命令会安装相应的模型和依赖库，运行时间较长。

.. Attention:: 如果长时间卡住，可以手动安装依赖库，eg(假定以下命令都在/home/路径下执行, GFPGAN可以换成其他的依赖库)：

    .. code:: bash

        ~# git clone https://github.com/TencentARC/GFPGAN.git
        ~# cd GFPGAN/
        ~# ./stable-diffusion-webui/venv/bin/python setup.py develop # 此处 python 应该为 venv 路径下的python










Mac 安装 Stable-Diffusion WebUI
--------------------------------------------------------------------------------