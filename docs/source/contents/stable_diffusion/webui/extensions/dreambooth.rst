.. _Dreambooth:

DreamBooth
================================================================================

GitHub repo: `Dreambooth Extension for Stable-Diffusion-WebUI <https://github.com/d8ahazard/sd_dreambooth_extension>`_

安装插件
--------------------------------------------------------------------------------

.. code:: bash

    cd extensions
    git clone https://github.com/d8ahazard/sd_dreambooth_extension.git

插件使用
--------------------------------------------------------------------------------

1. 打开 Dreambooth 标签页
#. 在 "Create Model" 子标签栏内, 输入新模型的名字, 选择加训得模型. 如果需要选择 HF 上的模型，可以填写为模型的URL 和 HF 的 Token, URL 形如 'runwayml/stable-diffusion-v1-5'
#. 加训得模型将会被保存在路径 models\\dreambooth\\MODELNAME\\working.
#. 点击 "Create" 按钮. 需要耗时一到两分钟，创建完毕后 UI 会提示模型文件夹已经被创建。

