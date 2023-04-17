.. _Control Net:

Control Net
================================================================================

GitHub repo: `sd-webui-controlnet <https://github.com/Mikubill/sd-webui-controlnet>`_

Stable-Diffusion WebUI ControlNet 和 T2I-Adapter 插件。

- `ControlNet <https://github.com/lllyasviel/ControlNet>`_
    - `ControlNet 模型 <https://huggingface.co/lllyasviel/ControlNet/tree/main/models>`_
- `T2I-Adapter <https://github.com/TencentARC/T2I-Adapter>`_
    - `T2I-Adapter 模型 <https://huggingface.co/TencentARC/T2I-Adapter>`_

安装插件
--------------------------------------------------------------------------------

1. 安装插件

.. code:: bash

    cd extensions
    git clone https://github.com/Mikubill/sd-webui-controlnet.git

2. 下载模型

.. code:: bash

    cd models/ControlNet
    wget model_download_url

模型网址：

- `lllyasviel/ControlNet-v1-1 <https://huggingface.co/lllyasviel/ControlNet-v1-1/tree/main>`_
- `webui/ControlNet-modules-safetensors <https://huggingface.co/webui/ControlNet-modules-safetensors/tree/main>`_
- `TencentARC/T2I-Adapter <https://huggingface.co/TencentARC/T2I-Adapter/tree/main/models>`_



插件使用
--------------------------------------------------------------------------------




ControlNet 模型训练
--------------------------------------------------------------------------------



参考资料
- `使用 diffusers 训练你自己的 ControlNet  <https://mp.weixin.qq.com/s/0qLMTbZmniMgP5keF0EUdw>`_
