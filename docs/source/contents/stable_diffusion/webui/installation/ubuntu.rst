.. _Ubuntu 安装 Stable Diffusion WebUI:

Ubuntu (Unix/Linux) 安装 Stable-Diffusion WebUI
================================================================================

环境准备
--------------------------------------------------------------------------------

1. 安装 git， wget

.. code:: bash

    # 安装 git
    apt install git
    # 验证git安装
    git --version

    # 安装 wget
    apt install wget
    # 验证 wget 安装
    wget --version

2. [可选] 安装会话管理工具 Tmux, Tmux 常用命令可查阅: `Tmux 常用命令 <https://zhuanlan.zhihu.com/p/90464490>`_.

.. code:: bash

    apt install tmux

3. 安装 Anaconda，从 Anaconda 下载最新的安装脚本并运行, Anaconda 是包含了 Python 安装包，具体可参阅: `Anaconda 官网 <https://www.anaconda.com/>`_。

.. code:: bash

    wget https://repo.anaconda.com/archive/Anaconda3-2023.03-Linux-x86_64.sh
    chmod 755 Anaconda3-2023.03-Linux-x86_64.sh
    ./Anaconda3-2023.03-Linux-x86_64.sh

安装完毕可进行 Python 安装环境验证

.. code:: bash

    python --version


Stable-Diffusion WebUI 安装
--------------------------------------------------------------------------------

1. 从 Github 上下载 Stable-Diffusion WebUI 代码

.. code:: bash

    git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git

2. 切换到 stable-diffusion-webui 文件夹下，修改 webui.sh 文件第59行 'can_run_as_root=1'
#. 运行命令 './webui.sh'，首次运行该命令会安装相应的模型和依赖库，运行时间较长。

.. Attention:: 如果长时间卡住，可以手动安装依赖库，eg(假定以下命令都在/home/路径下执行, GFPGAN可以换成其他的依赖库)：

    .. code:: bash

        git clone https://github.com/TencentARC/GFPGAN.git
        cd GFPGAN/
        ./stable-diffusion-webui/venv/bin/python setup.py develop # 此处 python 应该为 venv 路径下的python
