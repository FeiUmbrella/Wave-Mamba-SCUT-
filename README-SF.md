目录功能概览

* basicsr/：核心代码；archs/含各网络结构（WaveMamba等）、data/数据加载、losses/损失、models/训练封装、utils/通用工具；入口 basicsr/train.py (line 1)、basicsr/test.py (line 1)。
* options/：训练配置文件（options/train_wavemamba_uhdll.yml (line 1)、options/train_wavemamba_lol.yml (line 1)）。
* ckpt/：预训练权重（LOL、UHDLL、UHDLOL4K）。
* Figures/：论文插图与logo资源。
* inference_wavemamba.py (line 1)：推理脚本，加载权重并保存增强结果。
* comput_psnr_ssim.py (line 1)、test_metrics.py (line 1)：PSNR/SSIM计算与测试指标脚本。
* train.sh (line 1)、test.sh (line 1)：训练与推理的bash封装。
* requirements.txt (line 1)、setup.py (line 1)、VERSION (line 1)、LICENSE (line 1)：依赖、安装、版本与许可信息。
模型位置

* 核心架构实现位于 basicsr/archs/wavemamba_arch.py (line 1067)（定义WaveMamba、UNet、LFSSBlock/HFEBlock等，与图示框架对应）。
* 训练流程封装在 basicsr/models/uhdfour_model.py (line 22)（注册UHDModel，负责构建网络、加载权重、损失与指标）。
* 推理/评估入口 inference_wavemamba.py (line 1)，训练配置在 options/，预训练权重存于 ckpt/。