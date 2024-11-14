# 1.huggingface 模型下载
- 安装huggingface依赖
    ```
    # 安装transformers
    pip install transformers==4.38
    pip install sentencepiece==0.1.99
    pip install einops==0.8.0
    pip install protobuf==5.27.2
    pip install accelerate==0.33.0
    ```
- python代码从huggingface下载配置文件
    ```
    import os
    from huggingface_hub import hf_hub_download

    # 指定模型标识符
    repo_id = "internlm/internlm2_5-7b"

    # 指定要下载的文件列表
    files_to_download = [
        {"filename": "config.json"},
        {"filename": "model.safetensors.index.json"}
    ]

    # 创建一个目录来存放下载的文件
    local_dir = f"{repo_id.split('/')[1]}"
    os.makedirs(local_dir, exist_ok=True)

    # 遍历文件列表并下载每个文件
    for file_info in files_to_download:
        file_path = hf_hub_download(
            repo_id=repo_id,
            filename=file_info["filename"],
            local_dir=local_dir
        )
        print(f"{file_info['filename']} file downloaded to: {file_path}")
    ```
- 运行脚本
    ![](1-1.png)

## 2.json上传huggingface
```
# 建立huggingface仓库
git clone https://huggingface.co/langelo/intern_study_L0_4
```
![](2-1.png)
```
# 添加远程路径
git remote set-url origin https://langelo:hf_xxxxxxxxxxx@huggingface.co/blank/intern_study_L0_4

# git push
git add .
git commit -m "add:intern_study_L0_4"
git push
```
![](2-2.png)
可见仓库内添加了json文件

# 3.部署intern_cobuild
1. 选择created new space
    ![](3-1.png) 
2. 为space 命名并选择静态页面
    ![](3-2.png) 
3. 修改index.html
   ```
   <!doctype html>
    <html>
    <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>My static Space</title>
    <style>
        html, body {
        margin: 0;
        padding: 0;
        height: 100%;
        }
        body {
        display: flex;
        justify-content: center;
        align-items: center;
        }
        iframe {
        width: 430px;
        height: 932px;
        border: none;
        }
    </style>
    </head>
    <body>
    <iframe src="https://colearn.intern-ai.org.cn/cobuild" title="description"></iframe>
    </body>
    </html>
   ```
4. 上传修改后的代码
    ```
    # 添加远程路径
    git remote set-url origin https://langelo:hf_xxxxxxxxxxx@huggingface.co/blank/intern_study_L0_4

    # git push
    git add .
    git commit -m "add:intern_study_L0_4"
    git push
    ```
    最终结果
    ![](3-3.png)