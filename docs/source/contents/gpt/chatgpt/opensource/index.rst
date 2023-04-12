.. _ChatGPT 开源实现:


ChatGPT 开源实现
================================================================================

- `Dolly <https://github.com/databrickslabs/dolly.git>`_
- `ChatGLM-6B <https://github.com/THUDM/ChatGLM-6B>`_
- `OpenChatKit <https://github.com/togethercomputer/OpenChatKit.git>`_
- `Alpaca-LoRA <https://github.com/tloen/alpaca-lora.git>`_



- `GPT4All <https://github.com/nomic-ai/gpt4all.git>`_
- `BELLE: Be Everyone's Large Language model Engine <https://github.com/LianjiaTech/BELLE.git>`_
- `Stanford Alpaca: An Instruction-following LLaMA Model <https://github.com/tatsu-lab/stanford_alpaca.git>`_
- `骆驼(Luotuo): Chinese-alpaca-lora <https://github.com/LC1332/Chinese-alpaca-lora.git>`_


基础环境准备
--------------------------------------------------------------------------------

1. 安装显卡驱动

.. code:: bash

    # 查看系统版本
    lsb_release -a

    # 查看可用驱动版本
    ubuntu-drivers devices

    # 安装推荐驱动
    sudo apt install nvidia-driver-440
    # 重启系统
    sudo reboot
    # 重启后查看驱动
    nvidia-smi

    # 验证驱动是否安装
    cat /proc/driver/nvidia/version

2. 安装 CUDA Toolkit

1. 选择合适的 CUDA Toolkit 版本, 下载地址: `CUDA Toolkit <https://developer.nvidia.com/cuda-downloads>`_
#. 运行安装

.. code:: bash

    # Ubuntu 18.04 系统
    wget https://developer.download.nvidia.com/compute/cuda/12.1.0/local_installers/cuda_12.1.0_530.30.02_linux.run
    sudo 755 cuda_12.1.0_530.30.02_linux.run
    sudo sh cuda_12.1.0_530.30.02_linux.run --tookit --silent --override


.. Attention:: 下载模型

    - wget
    - git lfs + clone
    - huggface_hub

    .. code:: python

        from huggingface_hub import snapshot_download

        # bert-base-chinese 为 hugging_face  repo id
        snapshot_download(repo_id="bert-base-chinese")


ChatGPT 开源实现
--------------------------------------------------------------------------------


.. toctree::
    :maxdepth: 2

    chatglm_6b
    dolly
    alpaca_lora
    openchatkit

