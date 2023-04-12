.. _OpenChatKit:

OpenChatKit
================================================================================

1. 安装

.. code:: bash

    # 下载
    git clone https://github.com/togethercomputer/OpenChatKit.git
    # 创建环境
    cd OpenChatKit
    conda env create -f environment.yml -n openchatkit

    
2. 下载模型, 模型地址: `togethercomputer/Pythia-Chat-Base-7B <https://huggingface.co/togethercomputer/Pythia-Chat-Base-7B/tree/main>`_


3. 运行 bot

.. code:: bash

    # 假定模型保存在当前文件夹下的 Pythia-Chat-Base 文件夹中
    python inference/bot.py --model ./Pythia-Chat-Base-7B

