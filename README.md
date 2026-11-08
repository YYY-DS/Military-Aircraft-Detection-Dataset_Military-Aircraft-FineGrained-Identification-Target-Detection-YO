# 军事飞机检测数据集  | 军事飞机 细粒度识别 目标检测 YOLO格式 VOC格式 深度学习数据集 计算机视觉 航空器识别9110期

## 数据集概述

本数据集专注于**军事飞机型号的视觉检测与识别**，服务于军事航空研究、目标侦察及空域安全。数据涵盖34种经典军用飞机型号，从A10、B1、B2、B52到F22、F35等，适配细粒度目标检测、机型识别及航空器分类等任务。
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/05d716249712426d8965d28d879ac7f2.png)

## 数据集核心信息

| 数据要素 | 详细说明 |
| :--- | :--- |
| **类别** | 共 **34** 类军用飞机（详见下方列表） |
| **数量** | **4725** 张图像 |
| **格式** | 图像为 JPG/PNG；同时提供 **VOC**（XML）与 **YOLO**（txt）两种标注格式 |
| **配套文件** | 提供 `data.yaml` 配置文件，可直接导入训练 |
| **应用价值** | 1. **军事侦察**：支撑侦察图像中军用飞机型号的自动识别与分类。<br>2. **航空研究**：为民用航空管制、历史机型研究提供视觉数据基础。<br>3. **安防监控**：辅助机场、军事基地周边的飞行器类型识别与威胁评估。<br>4. **算法研发**：为细粒度目标检测、多类别航空器识别等任务提供大规模训练与评测数据。 |


![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/7cd3fb7948d44b1faa052b18b4184e2a.png)

## 完整类别列表（共34类）

| 序号 | 类别名称 | 序号 | 类别名称 | 序号 | 类别名称 |
|:---:|:---|:---:|:---|:---:|:---|
| 1 | A10 | 13 | F14 | 25 | RQ4 |
| 2 | B1 | 14 | F15 | 26 | Rafale |
| 3 | B2 | 15 | F16 | 27 | SR71 |
| 4 | B52 | 16 | F18 | 28 | Su57 |
| 5 | Be200 | 17 | F22 | 29 | Tu160 |
| 6 | C130 | 18 | F35 | 30 | Tu95 |
| 7 | C17 | 19 | F4 | 31 | U2 |
| 8 | C5 | 20 | J20 | 32 | US2 |
| 9 | E2 | 21 | JAS39 | 33 | V22 |
| 9 | EF2000 | 22 | MQ9 | 34 | XB70 |
| 11 | F117 | 23 | Mig31 | | YF23 |
| 12 | F14 | 24 | Mirage2000 | | |

## 数据三要素解析

**类别与机型覆盖**
*   数据集定义 **34** 类军用飞机型号，覆盖 **战斗机**（F14、F15、F16、F18、F22、F35、J20、Su57等）、**轰炸机**（B1、B2、B52、Tu160、Tu95等）、**运输机**（C130、C17、C5等）、**侦察机**（SR71、U2、RQ4、MQ9等）及 **特种机型**（V22鱼鹰、XB70等）。
*   类别设置涵盖了美国、俄罗斯、中国、欧洲等主要军事力量的经典型号，具有较强的代表性与研究价值。

**数据规模与格式**
*   图像总量约 **4725** 张，规模充足，能支撑多类别细粒度检测模型的稳健训练。
*   同时提供 **VOC** 与 **YOLO** 双格式标注，无需额外转换即可适配不同算法框架。
*   配套提供 **data.yaml 配置文件**，包含训练/验证路径与类别名称，用户可直接导入训练。

**应用与配套代码**
*   附赠**完整训练流程**：环境准备、数据集组织、YOLOv5训练命令。
*   附赠**推理代码**：单张图片推理、批量图片推理并保存结果。
*   附赠**用户界面（GUI）代码**：基于 PyQt5 构建，支持图片上传与检测结果可视化。
*   附赠**Web应用部署代码**：基于 Flask 框架搭建 API 接口，支持在线推理服务。

## 知识普及：细粒度军事飞机识别的技术要点

*   **类间相似性**：不同型号的战斗机在远距离或特定角度下形态相似（如F16与F18），模型需依赖机翼形状、进气道位置、尾翼构型等细节特征进行区分。
*   **尺度与姿态变化**：飞机在图像中的大小受拍摄距离影响显著，且俯视、侧视、仰视等角度会改变外观轮廓。需采用多尺度训练与视角增强策略。
*   **背景干扰**：天空、云层、地面等背景可能干扰检测，模型需学习鲁棒的纹理与形状特征。
*   **应用闭环**：检测结果可结合雷达、ADS-B数据，构建多传感器融合的航空器识别系统。

## 快速开始（代码示例）

**1. 准备配置文件 (`military_aircraft.yaml`)**
```yaml
train: ./data/MAD/images/train
val: ./data/MAD/images/test
nc: 34
names: ['A10', 'B1', 'B2', 'B52', 'Be200', 'C130', 'C17', 'C5', 'E2', 
        'EF2000', 'F117', 'F14', 'F15', 'F16', 'F18', 'F22', 'F35', 
        'F4', 'J20', 'JAS39', 'MQ9', 'Mig31', 'Mirage2000', 'RQ4', 
        'Rafale', 'SR71', 'Su57', 'Tu160', 'Tu95', 'U2', 'US2', 'V22', 
        'XB70', 'YF23']
```

**2. 启动 YOLOv8 训练**
```python
from ultralytics import YOLO

model = YOLO('yolov8m.pt')
model.train(
    data='military_aircraft.yaml',
    epochs=100,
    imgsz=640,
    batch=16,
    device=0
)
```

**3. 单张图片推理**
```python
import cv2
from ultralytics import YOLO

model = YOLO('runs/detect/train/weights/best.pt')
results = model.predict(source='test_image.jpg', conf=0.25)
for result in results:
    im_array = result.plot()
    im = cv2.cvtColor(im_array, cv2.COLOR_RGB2BGR)
    cv2.imshow("Detection Result", im)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```

**4. Web应用部署（Flask）**
```python
from flask import Flask, request, jsonify
from ultralytics import YOLO
import cv2
import numpy as np
from PIL import Image
import io
import base64

app = Flask(__name__)
model = YOLO('runs/detect/train/weights/best.pt')

@app.route('/predict', methods=['POST'])
def predict():
    file = request.files['image']
    img_bytes = file.read()
    img = Image.open(io.BytesIO(img_bytes))
    results = model.predict(source=img, conf=0.25)
    for result in results:
        im_array = result.plot()
        im = Image.fromarray(cv2.cvtColor(im_array, cv2.COLOR_BGR2RGB))
        img_byte_arr = io.BytesIO()
        im.save(img_byte_arr, format='PNG')
        img_byte_arr = img_byte_arr.getvalue()
    return jsonify({"status": "success", "result": base64.b64encode(img_byte_arr).decode('utf-8')}), 200

if __name__ == '__main__':
    app.run(debug=True)
```

## 标签
`军事飞机` `细粒度识别` `目标检测` `YOLO格式` `VOC格式` `深度学习数据集` `计算机视觉` `航空器识别`
