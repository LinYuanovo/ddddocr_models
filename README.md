

# DdddOcr 自训练验证码模型

此为开源项目[ddddocr训练工具](https://github.com/sml2h3/dddd_trainer)自己训练的验证码模型以及对应的数据集备份，实测效果还算不错，可以配合项目[ddddocr api](https://github.com/sml2h3/ocr_api_server)部署到云端实现自动化过验证码

## 目录

- [验证码展示](#验证码展示)
    - [今日校园](#今日校园)
    - [PikPak](#PikPak)

- [上手指南](#上手指南)
- [文件目录说明](#文件目录说明)

### 验证码展示

#### 今日校园

![image-20240606213525725](C:\Users\H\AppData\Roaming\Typora\typora-user-images\image-20240606213525725.png)

#### PikPak

![image-20240606213640110](C:\Users\H\AppData\Roaming\Typora\typora-user-images\image-20240606213640110.png)

### 上手指南

详细教程可以在[ddddocr-自定义ocr训练模型导入](https://github.com/sml2h3/ddddocr?tab=readme-ov-file#ⅴ-自定义ocr训练模型导入)看到

```python
import ddddocr

ocr = ddddocr.DdddOcr(det=False, ocr=False, import_onnx_path="pikpak.oonx", charsets_path="charsets.json")

with open('test.jpg', 'rb') as f:
    image_bytes = f.read()

print(ocr.classification(image_bytes))
```

### 文件目录说明

```
filetree 
│
├── /pikpak/            pikpak的乱序九宫格
│  ├── /model/
│  │  ├── pikpak.oonx   模型
│  │  ├── charsets.json 配置
│  ├── images.zip       数据集
├── /cpdaily/           今日校园的点选物体
│  ├── /model/
│  │  ├── cpdaily.oonx  模型
│  │  ├── charsets.json 配置
│  ├── images.zip       数据集
└── README.md
```

#### 

