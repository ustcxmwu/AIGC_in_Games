.. _Win 安装 Stable Diffusion WebUI:

Windows 安装 Stable-Diffusion WebUI
================================================================================


环境准备
--------------------------------------------------------------------------------

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



安装 Stable-Diffusion WebUI
--------------------------------------------------------------------------------

1. 从 github 上下载源代码

.. code:: bash

    ~ git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git
    
2. 切换到 standard-diffusion-webui 文件夹下，运行批处理文件 webui.bat
#. 打开 https://localhost:7860 页面展示 webui页面表示安装成功.

.. Attention:: 首次运行 webui.bat 会下载相应的模型和文件，如果运行不成功，可以多次运行 webui.bat 文件来进行修复.

