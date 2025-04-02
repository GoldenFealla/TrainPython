## 1. Cơ bản về Python và môi trường làm việc

### 1.1 Cài đặt Anaconda và Jupyter Notebook

#### Cài đặt Anaconda
- Tải Anaconda tại https://www.anaconda.com/download
- Next cho đến khi đến mục _**Advanced Installation Options**_ chọn _**Add Anaconda3 to my PATH environment**_
	![[Buổi 1 Ảnh 1.png]]
- Trước khi _**Finish**_ thì ta bỏ chọn _**Getting Started with Anaconda Distribution**_ 
	![[Buổi 1 Ảnh 2.png]]

#### Tạo môi trường với Anaconda 
##### Cách 1: Sử dụng Anaconda Navigator
- Mở **_Anaconda Navigator_** và chọn phần _**Environment**_
	![[Buổi 1 Ảnh 3.png]]
- Chọn _**Create**_
	![[Buổi 1 Ảnh 4.png]]
- Đặt tên cho môi trường và phiên bản Python
	![[Buổi 1 Ảnh 5.png]]
- Chọn _**Create**_ để tạo môi trường

##### Cách 2: Sử dụng Conda CLI
- Mở _**Terminal**_ bất kì nào
	![[Buổi 1 Ảnh 6.png]]
- Gõ theo cú pháp sau để tạo môi trường
```
conda create --name <tên môi trường>	
```

Ví dụ: `conda create --name demo`
	![[Buổi 1 Ảnh 7.png]]

#### Sử dụng môi trường cho việc lập trình
- Trước khi sử dụng được môi trường thì ta cần phải tích hợp conda vào terminal tương ứng bằng cách dùng lệnh. (Chỉ làm 1 lần)
```
conda init <Tên Terminal>
```

Ví dụ
```
#powershell (Window)
conda init powershell

#bash (Linux)
conda init bash

#zsh (Mac)
conda init zsh
```
Xem danh sách tại đây: https://docs.conda.io/projects/conda/en/stable/dev-guide/deep-dives/activation.html#conda-activate


> [!NOTE] Lưu ý
> Phải tắt terminal sau khi được tích hợp để sử dụng.
> Terminal khi được tích hợp sẽ luôn mở với môi trường base(root) khá là bất tiện khi ta cần dùng terminal cho việc phát triển bằng framework khác. Ta có thể tắt đó bằng cách dùng lệnh.
> `conda config --set auto_activate_base false`


- Sau khi tích hợp conda vào terminal thì ta chỉ cần dùng lệnh sau:
```
conda activate <tên môi trường>
```

Khi ta đang sử dụng môi trường thì sẽ có tên môi trường ở bên cạnh
![[Pasted image 20250402174207.png]]

- Để chạy chường trình python thì dùng lệnh
```
python <đường dẫn>
```

- Để thoát khỏi môi trường thì dùng lệnh
```
conda deactivate
```


### 1.2. Học cú pháp Python cơ bản (biến, kiểu dữ liệu, cấu trúc điều khiển)

- Biến và kiểu dữ liệu: int, float, string, boolean
```python
# Khai báo biến 
a = 10          # integer 
b = 3.14        # float 
c = "Pizza"     # string 
d = True        # boolean 
# In ra kiểu dữ liệu 
print(type(a), type(b), type(c), type(d))
```

- Cấu trúc dữ liệu: list, tuple, dictionary
```python
# List (mutable - có thể thay đổi) 
foods = ["pizza", "hamburger", "sushi"] 
print(foods[0])        # Truy cập phần tử đầu tiên 
foods.append("pasta")  # Thêm phần tử 

# Tuple (immutable - không thể thay đổi) 
coordinates = (10.5, 20.8) 

# Dictionary 
food_calories = {     
	"pizza": 300,    
	"hamburger": 250,    
	"salad": 100 
} 
print(food_calories["pizza"])  # Truy cập giá trị
```

-  Cấu trúc điều khiển: if-else, loops
```python
# If-else 
food = "pizza" 
if food == "pizza":     
	print("Yum!") 
else:     
	print("I prefer pizza")     
	
# For loop 
for item in foods:     
	print(item)     

# While loop 
count = 0 
while count < 3:     
	print(count)    
	count += 1
```

- Hàm cơ bản 
```python
# Định nghĩa hàm 
def is_pizza(food_name):     
	return food_name.lower() == "pizza" 
	
# Sử dụng hàm 
print(is_pizza("Pizza"))   # True 
print(is_pizza("Burger"))  # False 

# Hàm với tham số mặc định 
def describe_food(name, type="unknown"):
	return f"{name} is a {type} food" 

print(describe_food("Pizza", "Italian")) 
print(describe_food("Sushi"))  # Sử dụng giá trị mặc định
```

### 1.3. Thực hành với các bài tập đơn giản
- Tạo một danh sách 5 loại thức ăn khác nhau
- Viết hàm kiểm tra xem một món ăn có phải là pizza không
- Viết vòng lặp để kiểm tra từng món trong danh sách
- Tính số lượng pizza trong danh sách