# Xtuner
## 1.基座模型
基座模型是模型微调的基础，微调后的模型可以作为基座模型继续微调，需要大量数据训练。
基座模型壳从HuggingFace下载。


## 2.LoRA
LoRA 是一种轻量级的微调技术，可以显著降低微调所需显存占用。Xtuner 通过简单命令实现LoRA。

```
xtuner train ${CONFIG_NAME_OR_PATH}
```

也可以增加 deepspeed 进行训练加速：
```
xtuner train ${CONFIG_NAME_OR_PATH} --deepspeed deepspeed_zero2
```
生成Adaptor文件
```
mkdir hf
export MKL_SERVICE_FORCE_INTEL=1
export MKL_THREADING_LAYER=GNU
xtuner convert pth_to_hf ./internlm_chat_7b_qlora_oasst1_e3_copy.py ./work_dirs/internlm_chat_7b_qlora_oasst1_e3_copy/epoch_1.pth ./hf
```


## 2.LoRA与基座模型合并使用
```
xtuner convert merge ./internlm-chat-7b ./hf ./merged --max-shard-size 2GB
# xtuner convert merge \
#     ${NAME_OR_PATH_TO_LLM} \
#     ${NAME_OR_PATH_TO_ADAPTER} \
#     ${SAVE_PATH} \
#     --max-shard-size 2GB

```
