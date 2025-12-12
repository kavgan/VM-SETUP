# Important Commands

## Sometime installing pyenv more than once creates problem, in that case you can remove it first

sudo rm -rf /root/.pyenv

## Monitor GPU USAGE IN LINUX OS

watch -n 1 "nvidia-smi --query-gpu=index,name,utilization.gpu,utilization.memory,memory.used,memory.total --format=csv"
