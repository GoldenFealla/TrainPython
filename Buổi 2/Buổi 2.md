## Buổi 2: Xử lý dữ liệu với NumPy và Pandas

### <span style="color:darkblue">2.1. Làm việc với mảng và ma trận trong NumPy</span>

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

### <span style="color:darkblue">2.2. Xử lý dữ liệu với Pandas</span>

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

### <span style="color:darkblue">2.3. Thao tác cơ bản với hình ảnh</span>

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

### 2.4. Thực hành với các bài tập đơn giản

- **Bài tập với numpy**

  - Dùng numpy tạo mảng `[3, 6, 2, 9, 7, 2]` và hoàn thành các yêu cầu sau:

    - Tìm số nhỏ nhất, lớn nhất trong mảng
    - Tính tổng mảng
    - Tính trung bình mảng
    - Sắp xếp mảng

    <details>
      <summary style="color:green;font-weight:bold">Solution</summary>

    ```python
    import numpy as np

    # 0. Tạo mảng NumPy từ danh sách
    list = [3, 6, 2, 9, 7, 2]
    data = np.array(list)

    # 1. Tìm giá trị lớn nhất và nhỏ nhất trong mảng
    min_value = np.min(data)
    max_value = np.max(data)

    print("Min value:", min_value)  # Min value: 2
    print("Max value:", max_value)  # Max value: 9

    # 2. Tính tổng phần tử trong mảng
    sum_value = np.sum(data)
    print("Sum value:", sum_value)  # Sum value: 29

    # 3. Tính trung bình cộng của các phần tử trong mảng
    mean_value = np.mean(data)
    print("Mean value:", mean_value)  # Mean value: 4.833333333333333

    # 4 Sắp xếp mảng theo thứ tự tăng dần
    sorted_data = np.sort(data)
    print("Sorted data:", sorted_data)  # Sorted data: [2 2 3 6 7 9]
    ```

    </details>

  - Dùng numpy tạo một mảng ngẫu nhiên với kích thước 3x4 và hoàn thành các yêu cầu sau:

    - Tính tích vô hướng
    - Chuyển vị ma trận

    <details>
      <summary style="color:green;font-weight:bold">Solution</summary>

    ```python
    import numpy as np
    ```

    </details>

  - Dùng numpy tạo hai mảng `[1, 2, 3]`, `[4, 5, 6]` và hoàn thành các yêu cầu sau:

    - Nối hai mảng thành một mảng
    - Tách mảng vừa nối thành ba mảng

    <details>
      <summary style="color:green;font-weight:bold">Solution</summary>

    ```python
    import numpy as np
    ```

    </details>

- **Bài tập với pandas**

  - Dùng data sau

  ```python
  data = {
    'food': ['pizza', 'burger', 'pizza', 'salad', 'pasta', 'sushi', 'burger', 'pizza', 'steak', 'sandwich', 'pasta', 'burger', 'pizza', 'salad', 'pasta'],
    'price': [10, 8, 12, 7, 9, 15, 12, 15, 22, 7, 11, 9, 8, 9, 14],
    'calories': [300, 250, 320, 100, 280, 220, 400, 350, 450, 280, 320, 280, 290, 150, 400],
    'is_italian': [True, False, True, False, True, False, False, True, False, False, True, False, True, False, True]
  }
  ```

  - Tạo dataframe dừ data trên
  - In ra danh sách đồ ăn là pizza
  - In ra danh sách đồ ăn không phải là burger
  - In ra dach sách đồ ăn có giá trên 8
  - In ra danh sách đồ ăn có calories nhỏ hơn 200
  - In ra danh sách đồ ăn là món Ý

  <details>
    <summary style="color:green;font-weight:bold">Solution</summary>

  ```python
  import pandas as pd
  import numpy as np

  data = {
      'food': ['pizza', 'burger', 'pizza', 'salad', 'pasta', 'sushi', 'burger', 'pizza', 'steak', 'sandwich', 'pasta', 'burger', 'pizza', 'salad', 'pasta'],
      'price': [10, 8, 12, 7, 9, 15, 12, 15, 22, 7, 11, 9, 8, 9, 14],
      'calories': [300, 250, 320, 100, 280, 220, 400, 350, 450, 280, 320, 280, 290, 150, 400],
      'is_italian': [True, False, True, False, True, False, False, True, False, False, True, False, True, False, True]
  }

  # 1. Tạo dataframe dừ data trên
  df = pd.DataFrame(data)
  print("\nDataFrame: \n", df)

  # 2. In ra danh sách đồ ăn là pizza
  pizza = df[df['food'] == 'pizza']
  print("\nPizza: \n", pizza)

  # 3. In ra danh sách đồ ăn không phải là burger
  not_burger = df[df['food'] != 'burger']
  print("\nNot Burger: \n", not_burger)

  # 4. In ra dach sách đồ ăn có giá trên 8
  price = df[df['price'] > 8]
  print("\nPrice: \n", price)

  # 5. In ra danh sách đồ ăn có calories nhỏ hơn 200
  calories = df[df['calories'] < 200]
  print("\nCalories: \n", calories)

  # 6. In ra danh sách đồ ăn là món Ý
  italian = df[df['is_italian'] == True]
  italian = italian.drop_duplicates(subset=['food'])
  print("\nItalian: \n", italian)
  ```

  </details>

- **Bài tập với ảnh (Không bắt buộc)**

  - Dùng ảnh `pizza.jpg` đã cho hãy điều chỉnh ảnh theo yêu cầu sau (Dùng sườn code bên dưới)

    - Cài đặt `matplotlib` trước khi sử dụng

    ```
    conda install matplotlib
    ```

    - Sườn code

    ```python
    import numpy as np
    import matplotlib.pyplot as plt
    from PIL import Image

    # Đọc hình ảnh (cần chuẩn bị một hình pizza)
    img = Image.open('pizza.jpg')

    # Chuyển về mảng NumPy
    img_array = np.array(img)
    adjusted_img = img_array.copy()

    # Điều chỉnh ảnh theo yêu cầu đề bài bắt cách dùng biến adjusted_img
    # Điều chỉnh ở đây

    # Hiển thị hình ảnh gốc và hình ảnh đã điều chỉnh
    plt.figure(figsize=(10, 5))
    plt.subplot(1, 2, 1)
    plt.title('Adjusted Image')
    plt.imshow(adjusted_img)
    plt.axis('off')
    plt.subplot(1, 2, 2)
    plt.title('Original Image')
    plt.imshow(img_array)
    plt.axis('off')
    plt.show()
    ```

    > Gợi ý: Một pixel màu là 8bit. Tương đương có 256 giá trị. Những màu có giá trị cao hơn ở giữa sẽ càng cao và ngược lại

  - Tăng độ sáng (Brightness) ảnh lên 50%
    <details>

    <summary style="color:green;font-weight:bold">Solution</summary>

    ```python
    import numpy as np
    import matplotlib.pyplot as plt
    from PIL import Image

    # Đọc hình ảnh (cần chuẩn bị một hình pizza)
    img = Image.open('pizza.jpg')

    # Chuyển về mảng NumPy
    img_array = np.array(img)
    adjusted_img = img_array.copy()

    # Điều chỉnh ảnh theo yêu cầu đề bài bắt cách dùng biến adjusted_img
    # Điều chỉnh ở đây
    adjusted_img = np.clip(np.dot(adjusted_img, 1.5), 0, 255).astype(np.uint8)

    # Hiển thị hình ảnh gốc và hình ảnh đã
    plt.figure(figsize=(10, 5))
    plt.subplot(1, 2, 1)
    plt.title('Adjusted Image')
    plt.imshow(adjusted_img)
    plt.axis('off')
    plt.subplot(1, 2, 2)
    plt.title('Original Image')
    plt.imshow(img_array)
    plt.axis('off')
    plt.show()
    ```

    </details>

  - Giảm tương phản (Contrast) ảnh xuống 25%

    > Gợi ý: Để giảm tương phản thì giá trị màu của pixel nào sáng thì càng sáng, tối thì càng tối. Lấy giá trị 128 làm cột mốc sáng tối của pixcel

    <details>

    <summary style="color:green;font-weight:bold">Solution</summary>

    ```python
    import numpy as np
    import matplotlib.pyplot as plt
    from PIL import Image

    # Đọc hình ảnh (cần chuẩn bị một hình pizza)
    img = Image.open('pizza.jpg')

    # Chuyển về mảng NumPy
    img_array = np.array(img)
    adjusted_img = img_array.copy()  # Chuyển đổi sang kiểu float32 để tránh tràn số nguyên

    # Điều chỉnh ảnh theo yêu cầu đề bài bắt cách dùng biến adjusted_img
    # Điều chỉnh ở đây
    middle_color = 128.

    adjusted_img = adjusted_img.astype(np.float32)
    adjusted_img = np.clip(middle_color + 0.75 * (img_array - middle_color), 0, 255).astype(np.uint8)

    # Hiển thị hình ảnh gốc và hình ảnh đã điều chỉnh
    plt.figure(figsize=(10, 5))
    plt.subplot(1, 2, 1)
    plt.title('Adjusted Image')
    plt.imshow(adjusted_img)
    plt.axis('off')
    plt.subplot(1, 2, 2)
    plt.title('Original Image')
    plt.imshow(img_array)
    plt.axis('off')
    plt.show()
    ```

    </details>

  - Tăng độ bão hòa (Saturation) ảnh lên 35%

    > Gợi ý: Để tăng màu sắc hay con gọi độ bảo hòa thì ta cần giảm bớt giá trị đen trắng (greyscale?)

    <details>

    <summary style="color:green;font-weight:bold">Solution</summary>

    ```python
    import numpy as np
    import matplotlib.pyplot as plt
    from PIL import Image

    # Đọc hình ảnh (cần chuẩn bị một hình pizza)
    img = Image.open('pizza.jpg')

    # Chuyển về mảng NumPy
    img_array = np.array(img)
    adjusted_img = img_array.copy()

    # Điều chỉnh ảnh theo yêu cầu đề bài bắt cách dùng biến adjusted_img
    # Điều chỉnh ở đây
    if len(img_array.shape) == 3:  # RGB image
        adjusted_img = np.mean(img_array, axis=2, keepdims=True)
        adjusted_img = np.dot(img_array, 2) + np.dot(adjusted_img, 1 - 2)
        adjusted_img = np.clip(adjusted_img, 0, 255).astype(np.uint8)

    # Hiển thị hình ảnh gốc và hình ảnh đã điều chỉnh
    plt.figure(figsize=(10, 5))
    plt.subplot(1, 2, 1)
    plt.title('Adjusted Image')
    plt.imshow(adjusted_img)
    plt.axis('off')
    plt.subplot(1, 2, 2)
    plt.title('Original Image')
    plt.imshow(img_array)
    plt.axis('off')
    plt.show()
    ```

    </details>

  - Làm mờ ảnh đi 20%

    > Gợi ý: Làm mờ ảnh bằng cách tính giá trị trung bình của vị trí của từng pixels trong bán kính cho trước.
    >
    > - Vòng vàng là pixel hiện tại cần tính
    > - Vòng đỏ là vùng để tính giá trị trung bình cho pixcel hiện tại

    ![how-simple-blue-work.gif](./how-simple-blur-work.gif)

    <details>

    <summary style="color:green;font-weight:bold">Solution</summary>

    ```python
    import numpy as np
    import matplotlib.pyplot as plt
    from PIL import Image

    # Đọc hình ảnh (cần chuẩn bị một hình pizza)
    img = Image.open('pizza.jpg')

    # Chuyển về mảng NumPy
    img_array = np.array(img)
    adjusted_img = img_array.copy()

    # Điều chỉnh ảnh theo yêu cầu đề bài bắt cách dùng biến adjusted_img
    # Điều chỉnh ở đây
    adjusted_img = img_array.copy()
    height, width, channels = img_array.shape
    # Kích thước ô vuông để tính trung bình
    pad = 5

    # Lặp từng pixel
    for y in range(pad, height - pad):
        for x in range(pad, width - pad):
            # Lặp từng chanel màu (R, G, B)
            for c in range(channels):
                adjusted_img[y, x, c] = np.mean(img_array[y - pad:y + pad + 1, x - pad:x + pad + 1, c])

    # Hiển thị hình ảnh gốc và hình ảnh đã điều chỉnh
    plt.figure(figsize=(10, 5))
    plt.subplot(1, 2, 1)
    plt.title('Adjusted Image')
    plt.imshow(adjusted_img)
    plt.axis('off')
    plt.subplot(1, 2, 2)
    plt.title('Original Image')
    plt.imshow(img_array)
    plt.axis('off')
    plt.show()
    ```

    </details>
