import cv2
import numpy as np
import matplotlib.pyplot as plt
import random

def create(img):
    try:  
        #显示彩图
        img_RGB = cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
        plt.imshow(img_RGB)
        plt.show()
    except: 
        #显示灰度图或黑白图
        plt.imshow(img,cmap="gray")
        plt.show()

# 生成初始画布
h = 1024
w = 1024
img = 255 * np.ones((h ,w , 3), dtype=np.uint8)

operator_mapping = {
    "|": lambda x, y: x | y,
    "&": lambda x, y: x & y,
    "+": lambda x, y: x + y,
    "-": lambda x, y: x - y,
    "^": lambda x, y: x ^ y,
}

operator1 = random.choice(list(operator_mapping.keys()))
operator2 = random.choice(list(operator_mapping.keys()))
operator3 = random.choice(list(operator_mapping.keys()))

number1 = random.randint(200, 255)
number2 = random.randint(200, 255)
number3 = random.randint(200, 255)

# 万花筒启动
for i in range(h):
    for j in range(w):      
        # 生成色彩缤纷的万花筒图案
        img[i,j,2] = operator_mapping[operator1](i%j,j%i)&number1 if (i&j) else 0
        img[i,j,1] = operator_mapping[operator2](i%j,j%i)&number2 if (i&j) else 0
        img[i,j,0] = operator_mapping[operator3](i%j,j%i)&number3 if (i&j) else 0

# 绘制
create(img)
