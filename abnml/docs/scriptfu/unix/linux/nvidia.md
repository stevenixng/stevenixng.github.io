---
title: nvidia
---

### patch nvidia card for multiple streams
If the nvidia driver gets updated, you'll need to repatch the driver to unlock multiple nvenc. Code is at <https://github.com/keylase/nvidia-patch/>

#### Check nvidia driver version:
    nvidia-smi

#### Apply patch:
    sudo /home/stevenix/opt/nvidia-patch/patch.sh
