## Buổi 2: Xử lý dữ liệu với NumPy và Pandas

### 2.1. Làm việc với mảng và ma trận trong NumPy

#### Cài đặt Numpy

- Trước khi sử dụng _**NumPy**_ ta cần cài đặt đầu tiên
- Activate môi trường sử dụng. (Ở đây sử dụng môi trường demo)

```
conda activate demo
```

- Cài đặt _**NumPy**_ vào môi trường

```
conda install conda-forge::numpy
```

Danh sách packages do conda cung cấp: https://conda-forge.org/packages/

#### Sử dụng NumPy

```python
import numpy as np

#==================== Vài phương thức tạo mạng ====================#
normal_array = np.array([1, 2, 3, 4, 5])
print(normal_array)
# > [1 2 3 4 5]

array_of_zero = np.zeros(3) # Mảng có 3 phần tử là 0
print(array_of_zero)
# > [0. 0. 0.]

array_of_one = np.ones(4)   # Mảng có 4 phần tử là 1
print(array_of_one)
# [1. 1. 1. 1.]

array_of_random = np.random.rand(5, 5) # Mảng ngẫu nhiên 5x5
print(array_of_random)
# [[0.10630251 0.30925763 0.81840997 0.32815268 0.18682397]
# [0.1776548  0.57883537 0.13165102 0.38386888 0.85445249]
# [0.9172498  0.39242814 0.45772158 0.08646415 0.62076516]
# [0.88734336 0.44404186 0.68553524 0.23679066 0.40152148]
# [0.08024502 0.70811933 0.01916566 0.34406042 0.13115162]]

#======================= Truy xuất mạng =======================#
print(normal_array[2:4]) # Lấy giá trị mảng từ vị trí 2 đến vị trí 4 trong mảng
# > [3 4]

print(normal_array[2:]) # Lấy giá trị mảng từ vị trí 2 về cuối mảng
# > [3 4 5]

print(normal_array[:4]) # Lấy giá trị mảng từ đầu mảng đến vị trí 4 trong mảng
# > [1 2 3 4]

#======================= Thao tác với mạng =======================#
# Các phép toán
print(normal_array * 2) # Nhân mỗi phần tử với 2
# > [2 4 6 8 10]

print(normal_array + 10) # Cộng mỗi phần tử với 10
# > [11 12 13 14 15]

#=========================== Thống kê ============================#
print(np.mean(normal_array))  # Giá trị trung bình
# > 3.0

print(np.max(normal_array))   # Giá trị lớn nhất
# > 5

print(np.min(normal_array))   # Giá trị nhỏ nhất
# > 1
```

Danh sách các phương thức hay sử dụng: [Danh sách](./np_common.md)

### 2.2. Xử lý dữ liệu với Pandas

#### Cài đặt PandasNumpy

- Trước khi sử dụng _**Pandas**_ ta cần cài đặt đầu tiên
- Activate môi trường sử dụng. (Bỏ qua nếu đã activate)

```
conda activate demo
```

- Cài đặt _**Pandas**_ vào môi trường

```
conda install conda-forge::pandas
```

#### Sử dụng Pandas

```python
import pandas as pd


#==================== Series và DataFrame ====================#
# Series là dạng kiểu dữ liệu cho một cột duy nhất
# Tạo Series
s = pd.Series([1, 3, 5, np.nan, 6, 8])
print(s)
# > 0    1.0
#   1    3.0
#   2    5.0
#   3    NaN
#   4    6.0
#   5    8.0


# DataFrame là dạng kiểu dữ liệu cho nhiều cột
# Tạo DataFrame
data = {
	'food': ['pizza', 'burger', 'pizza', 'salad', 'pasta'],
	'price': [10, 8, 12, 7, 9],
	'calories': [300, 250, 320, 100, 280],
	'is_italian': [True, False, True, False, True]
}

df = pd.DataFrame(data)
print(df)
# >     food   price  calories  is_italian
#   0   pizza     10       300        True
#   1   burger     8       250       False
#   2   pizza     12       320        True
#   3   salad      7       100       False
#   4   pasta      9       280        True

#==================== Lọc và nhóm dữ liệu ====================#
# Lọc dữ liệu
pizza_df = df[df['food'] == 'pizza']
print(pizza_df)
# >    food   price  calories  is_italian
#   0  pizza     10       300        True
#   2  pizza     12       320        True

# Thống kê theo nhóm
print(df.groupby('food').mean())
# >          price  calories  is_italian
#    food
#    burger    8.0     250.0         0.0
#    pasta     9.0     280.0         1.0
#    pizza    11.0     310.0         1.0
#    salad     7.0     100.0         0.0

# Tính toán cơ bản
print(df['calories'].mean()) # Trung bình calories
# > 250.0

print(df['price'].max())     # Giá cao nhất
# > 12
```

### 2.3. Thao tác cơ bản với hình ảnh

#### Cài đặt matplotlib

- Cài đặt _**matplotlib**_ vào môi trường

```
conda install conda-forge::matplotlib
```

#### Thao tác với hình ảnh

[Tải ảnh tại đây](https://github.com/GoldenFealla/TrainPython/blob/master/pizza.jpg)

- Hiện thị ảnh lên màn hình

```python
import numpy as np
import matplotlib.pyplot as plt
from PIL import Image

# Đọc hình ảnh (cần chuẩn bị một hình pizza)
img = Image.open('pizza.jpg')

# Chuyển về mảng NumPy
img_array = np.array(img)
print(img_array.shape)  # (height, width, channels)
# > (635, 640, 3)

plt.imshow(img_array)
plt.axis('off')
plt.show()
```

Kết quả:
![Buổi 2 Ảnh 1.png](Buổi%202%20Ảnh%201.png)

- Biến ảnh về dạng Greyscale

```python
import numpy as np
import matplotlib.pyplot as plt
from PIL import Image

# Đọc hình ảnh (cần chuẩn bị một hình pizza)
img = Image.open('pizza.jpg')

# Chuyển về mảng NumPy
img_array = np.array(img)
print(img_array.shape)  # (height, width, channels)

# Chuyển sang ảnh grayscale
if len(img_array.shape) == 3:  # RGB image
    gray_img = np.mean(img_array, axis=2).astype(np.uint8)
   
plt.imshow(gray_img, cmap='grey')
plt.axis('off')
plt.show()
```

Kết quả:
![Buổi 2 Ảnh 2.png](Buổi%202%20Ảnh%202.png)

- Cắt ảnh

```python
import numpy as np
import matplotlib.pyplot as plt
from PIL import Image

# Đọc hình ảnh (cần chuẩn bị một hình pizza)
img = Image.open('pizza.jpg')

# Chuyển về mảng NumPy
img_array = np.array(img)
print(img_array.shape)  # (height, width, channels)

# Cắt hình ảnh (crop)
height, width = img_array.shape[:2]
cropped_img = img_array[height//4:3*height//4, width//4:3*width//4]

plt.imshow(cropped_img)
plt.axis('off')
plt.show()
```

Kết quả:
![Buổi 2 Ảnh 3.png](Buổi%202%20Ảnh%203.png)
