# 1. np.array() - Tạo mảng từ danh sách python
- Được dùng để tạo mảng từ danh sách có sẵn của Python được tạo từ trước.
- Hữu ích trong việc tạo mảng từ danh sách có sẵn của Python trước khi dùng các hàm có sẵn của numpy để tăng tốc sử lý

Documentation: [numpy.array](https://numpy.org/doc/stable/reference/generated/numpy.array.html)


```python
import numpy as np

list_data = [1, 2, 3, 4, 5]
arr = np.array(list_data)

print("Result:", arr)
```

    Result: [1 2 3 4 5]
    

# 2. np.zeros() - Tạo mảng với mỗi phần tử là 0
- Được dùng để tạo mảng với mỗi phần tử trong mảng là 0 trước khi tính toán phức tạp tiếp theo.
- Hữu ích khi cần tạo mảng trống với giá trị mặc định là 0 trước khi xử lý các thuật toán phức tạp (Ví dụ: Longest common subsequence,...).

Documentation: [numpy.zeros](https://numpy.org/doc/stable/reference/generated/numpy.zeros.html)


```python
import numpy as np

one_dimension_zeros_arr = np.zeros(2) # Creates array of 2 zeros
print("\nResult one dimension:\n", one_dimension_zeros_arr)

two_dimensions_zeros_arr = np.zeros((2, 3))  # Creates a 3x4 array of zeros
print("\nResult two dimensions:\n", two_dimensions_zeros_arr)

three_dimensions_zeros_arr = np.zeros((2, 3, 4))  # Creates a 2x3x5 array of zeros
print("\nResult three dimensions:\n", three_dimensions_zeros_arr)
```

    
    Result one dimension:
     [0. 0.]
    
    Result two dimensions:
     [[0. 0. 0.]
     [0. 0. 0.]]
    
    Result three dimensions:
     [[[0. 0. 0. 0.]
      [0. 0. 0. 0.]
      [0. 0. 0. 0.]]
    
     [[0. 0. 0. 0.]
      [0. 0. 0. 0.]
      [0. 0. 0. 0.]]]
    

# 3. np.ones() - Tạo mảng với mỗi phần tử là 1
- Được dùng để tạo mảng với mỗi phần tử trong mảng là 1 trước khi tính toán phức tạp tiếp theo
- Hữu ích khi cần tạo mảng trống với giá trị mặc định là 1 trước khi xử lý các thuật toán phức tạp (Ví dụ: Product of Array Except Self,...).

Documentation: [numpy.ones](https://numpy.org/doc/stable/reference/generated/numpy.ones.html)


```python
import numpy as np

one_dimension_ones_arr = np.ones(2) # Creates array of 2 ones
print("\nResult one dimension:\n", one_dimension_ones_arr)

two_dimensions_ones_arr = np.ones((2, 3))  # Creates a 3x4 array of ones
print("\nResult two dimensions:\n", two_dimensions_ones_arr)

three_dimensions_ones_arr = np.ones((2, 3, 4))  # Creates a 2x3x5 array of ones
print("\nResult three dimensions:\n", three_dimensions_ones_arr)
```

    
    Result one dimension:
     [1. 1.]
    
    Result two dimensions:
     [[1. 1. 1.]
     [1. 1. 1.]]
    
    Result three dimensions:
     [[[1. 1. 1. 1.]
      [1. 1. 1. 1.]
      [1. 1. 1. 1.]]
    
     [[1. 1. 1. 1.]
      [1. 1. 1. 1.]
      [1. 1. 1. 1.]]]
    

# 4. np.arange() - Tạo mảng có khoảng cách định sẵn
- Được dùng để tạo mảng với những giá trị có trình tự cho trước. Giống với hàm range() trong Python
- Hữu ích trong việc lưới tọa độ để vẽ và trực quan hóa (Vẽ đồ thị trong đó trục x, y hiện thị giá trị tăng không đổi), v.v...

Documentation: [numpy.arange](https://numpy.org/doc/stable/reference/generated/numpy.arange.html)


```python
import numpy as np

sequence = np.arange(0, 10, 1)  # Start 0, stop 10, step 1
print("\nResult start 0, stop 10, step 1:\n", sequence)

sequence = np.arange(0, 10, 2)  # Start 0, stop 10, step 2
print("\nResult start 0, stop 10, step 2:\n", sequence)

sequence = np.arange(0, 10, 3)  # Start 0, stop 10, step 3
print("\nResult start 0, stop 10, step 3:\n", sequence)
```

    
    Result start 0, stop 10, step 1:
     [0 1 2 3 4 5 6 7 8 9]
    
    Result start 0, stop 10, step 2:
     [0 2 4 6 8]
    
    Result start 0, stop 10, step 2:
     [0 3 6 9]
    

# 5. np.linspace() - Tạo mảng có phân bố đều
- Được dùng để tạo mảng có phân bố đều.
- Hữu ích trong việc cần tạo mảng có phân bố đều để thao túng dữ liệu (Color mapping, Parametric curves,...)

Documentation: [numpy.linspace](https://numpy.org/doc/stable/reference/generated/numpy.linspace.html)


```python
import numpy as np

linear_space = np.linspace(7, 12, 6)  # Start 7, stop 12, 5 points
print("\nResult start 7, stop 12, 6 points:\n", linear_space)

linear_space = np.linspace(1.2, 1.6, 5)  # Start 1.2, stop 1.6, 5 points
print("\nResult start 1.2, stop 1.6, 5 points:\n", linear_space)

linear_space = np.linspace(-9, -2, 8)  # Start -9, stop -2, 8 points
print("\nResult start -9, stop -2, 8 points:\n", linear_space)
```

    
    Result start 7, stop 12, 6 points:
     [ 7.  8.  9. 10. 11. 12.]
    
    Result start 1.2, stop 1.6, 5 points:
     [1.2 1.3 1.4 1.5 1.6]
    
    Result start -9, stop -2, 8 points:
     [-9. -8. -7. -6. -5. -4. -3. -2.]
    

# 6. np.random.rand() - Tạo mảng với giá trị ngẫu nhiên
- Được dùng cho việc mô phỏng hoặc khởi tạo mạng lưới nơ-ron.
- Hữu ích trong việc cần tạo mảng ngẫu nhiên để thao túng dữ liệu (Adding Noise,...)

Documentation: [numpy.random.rand](https://numpy.org/doc/stable/reference/random/generated/numpy.random.rand.html)


```python
import numpy as np

random_array = np.random.rand(3)  # one dimension array of random values between 0 and 1
print("\nResult one dimension:\n", random_array)

random_array = np.random.rand(3, 2)  # two dimensions array of random values between 0 and 1
print("\nResult two dimension:\n", random_array)

random_array = np.random.rand(3, 2, 4)  # three dimensions array of random values between 0 and 1
print("\nResult three dimension:\n", random_array)
```

    
    Result one dimension:
     [0.17065352 0.61857501 0.49997405]
    
    Result two dimension:
     [[0.07578904 0.58402761]
     [0.39323379 0.831058  ]
     [0.83480522 0.172774  ]]
    
    Result three dimension:
     [[[0.09499147 0.79761075 0.1720163  0.79778598]
      [0.97018009 0.05978156 0.90790077 0.46183134]]
    
     [[0.5676455  0.64201734 0.33746997 0.39388645]
      [0.6687082  0.95150874 0.5661078  0.88946219]]
    
     [[0.74422573 0.76759907 0.92056626 0.23513927]
      [0.91391184 0.29818987 0.04744017 0.39500184]]]
    

# 7. np.mean() - Tính trung bình của mảng
- Được dùng trong thống kê, phân tích dữ liệu và sử lý tín hiệu
- Hữu ích trong việc tính giá trị trung bình một cách nhanh chóng (Image Noise Reduction, Batch Normalization,...)

Documentation: [numpy.mean](https://numpy.org/doc/stable/reference/generated/numpy.mean.html)


```python
import numpy as np

data = np.array([1, 2, 3, 4, 5])
mean_value = np.mean(data)
print("\nResult:", mean_value)
```

    
    np.mean(): 3.0
    

# 8. np.median() - Tìm phần tử có giá trị nằm giữa
- Được dùng trong thống kê, đặc biệt là với các phân phối lệch
- Hữu ích trong việc tìm phần tử có giá trị nằm giữa nhằm mục đích xử lý dữ liệu (Reduce Image Noise,...)

Documentation: [numpy.median](https://numpy.org/doc/stable/reference/generated/numpy.median.html)


```python
import numpy as np

skewed_data = np.array([9, 2, 3, 6, 5])
median_value = np.median(skewed_data)
print("\nResult:", median_value)
```

    
    Result: 5.0
    

# 9. np.min() and np.max() - Tìm giá trị thấp và cao nhất
- Được dùng trong phân tích dữ liệu và tiền sử lý
- Hữu ích trong việc tìm giá trị thấp nhất và cao nhất cho việc xử lý dữ liệu (Outlier detection, Calculating ranges and boundaries,...)

Documentation: [numpy.min](https://numpy.org/doc/stable/reference/generated/numpy.min.html), [numpy.max](https://numpy.org/doc/stable/reference/generated/numpy.max.html)


```python
import numpy as np

data = [6, 9, 8, 1, 7, 2]

min_value = np.min(data)
max_value = np.max(data)

print("\nResult min:", min_value)
print("Result max:", max_value)
```

    
    Result min: 1
    Result max: 9
    

# 10. np.argmin() and np.argmax() - Tìm vị trí của giá trị thấp và cao nhất
- Được dùng để xác định vị trí cực trị trong dữ liệu

Documentation: [numpy.min](https://numpy.org/doc/stable/reference/generated/numpy.argmin.html), [numpy.max](https://numpy.org/doc/stable/reference/generated/numpy.argmax.html)


```python
import numpy as np

data = [6, 9, 8, 1, 7, 2]

argmin_value = np.argmin(data)
argmax_value = np.argmax(data)

print("\nnp.argmin():", argmin_value)
print("np.argmax():", argmax_value)
```

    
    np.argmin(): 3
    np.argmax(): 1
    

# 11. np.sum() - Tính tổng mảng
- Được dùng trong thống kê và tổng hợp dữ liệu

Documentation: [numpy.sum](https://numpy.org/doc/stable/reference/generated/numpy.sum.html)


```python
import numpy as np

data = [1, 2, 3, 4, 5]
total = np.sum(data)

print("\nnp.sum():", total)
```

    
    np.sum(): 15
    

# 12. np.sort() - Sắp xếp mảng
- Được dùng để sắp xếp dữ liệu để phân tích hoặc trực quan hóa

Documentation: [numpy.sort](https://numpy.org/doc/stable/reference/generated/numpy.sort.html)


```python
import numpy as np

unsorted = np.array([3, 1, 4, 1, 5, 9, 2])
sorted_arr = np.sort(unsorted)

print("\nOriginal:", unsorted)
print("Result:", sorted_arr)
```

    
    Original: [3 1 4 1 5 9 2]
    Result: [1 1 2 3 4 5 9]
    

# 13. np.log(), np.log2() and np.log10() - Tính logarit
- Được dùng trong chuyển đổi dữ liệu và tính toán khoa học

Documentation: [numpy.log](https://numpy.org/doc/stable/reference/generated/numpy.log.html), [numpy.log2](https://numpy.org/doc/stable/reference/generated/numpy.log2.html), [numpy.log10](https://numpy.org/doc/stable/reference/generated/numpy.log10.html)


```python
import numpy as np

log_values = np.log(np.array([1, np.e, np.e**2]))  # Natural logarithm
log2_values = np.log2(np.array([1, 2, 512]))       # Base-2 logarithm
log10_values = np.log10(np.array([1, 10, 100]))    # Base-10 logarithm

print("\nResult natural:", log_values)
print("Result base 2: ", log2_values)
print("Result base 10:", log10_values)
```

    
    Result natural: [0. 1. 2.]
    Result base 2:  [0. 1. 9.]
    Result base 10: [0. 1. 2.]
    

# 14. np.dot() - Tính tích vô hướng
- Được dùng trong đại số tuyến tính, xử lý tín hiệu và học máy

Documentation: [numpy.dot](https://numpy.org/doc/stable/reference/generated/numpy.dot.html)


```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
dot_product = np.dot(a, b)  # 1*4 + 2*5 + 3*6

print("\nResult dot product:", dot_product)
```

    
    Result dot product: 32
    

# 15. np.transpose() - Chuyển vị ma trận
- Được dùng trong đại số tuyến tính và định hình lại dữ liệu

Documentation: [numpy.transpose](https://numpy.org/doc/stable/reference/generated/numpy.transpose.html)


```python
import numpy as np

matrix = np.array([[1, 2, 3], [4, 5, 6]])
transposed = np.transpose(matrix)  

print("\nOriginal:\n", matrix)
print("Result:\n", transposed)
```

    
    Original:
     [[1 2 3]
     [4 5 6]]
    Result:
     [[1 4]
     [2 5]
     [3 6]]
    

# 16. np.concatenate() - Nối mảng lại thành một mảng
- Được dùng khi kết hợp các tập dữ liệu hoặc xây dựng các mảng phức tạp

Documentation: [numpy.concatenate](https://numpy.org/doc/stable/reference/generated/numpy.concatenate.html)


```python
import numpy as np

arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
concatenated = np.concatenate((arr1, arr2))

print("\nResult:", concatenated)
```

    
    Result: [1 2 3 4 5 6]
    

# 17. np.split() - Tách mảng
- Được dùng để chia dữ liệu thành các bộ kiểm tra hoặc huấn luyện hoặc xử lý theo từng đợt

Documentation: [numpy.split](https://numpy.org/doc/stable/reference/generated/numpy.split.html)


```python
import numpy as np

array_to_split = np.arange(9)
split_result = np.split(array_to_split, 3)  # Split into 3 equal parts

print("\nOriginal:", array_to_split)
print("Result:", split_result)
```

    
    Original: [0 1 2 3 4 5 6 7 8]
    Result: [array([0, 1, 2]), array([3, 4, 5]), array([6, 7, 8])]
    
