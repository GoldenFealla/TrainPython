# Buổi 3: Giới thiệu về AI và Chuẩn bị Dataset, Environment

## 3.1. Giới thiệu về AI

### AI (Artificial Intelligence - Trí tuệ nhân tạo)

- **AI (_Artificial Intelligence_ - Trí tuệ nhân tạo)**: đề cập đến khả năng của các hệ thống máy tính thực hiện các nhiệm vụ liên quan đến trí thông minh của con người, như học tập, suy luận, giải quyết vấn đề, nhận thức và đưa ra quyết định. [wiki➚](https://vi.wikipedia.org/wiki/Tr%C3%AD_tu%E1%BB%87_nh%C3%A2n_t%E1%BA%A1o)

- Nói đơn giản hơn **AI** khiến Máy Tính hoạt động giống con người hơn mà không cần biết chúng làm bằng cách nào.

- Những phần nhỏ hơn của **AI** (**_Subset of AI_**):
  - **Machine Learning** (ML): Sử dụng các **thuật toán** và **mô hình thống kê** mà không cần lập trình rõ ràng. Các hệ thống Machine Learning học từ các mẫu dữ liệu để đưa ra các dự đoán và quyết định.
    - Recommendation systems (_Youtube, Spotify,..._)
    - Email spam filters (_Gmail,..._)
    - ...
  - **Deep Learning** (DL): Là phần nhỏ hơn của Machine Learning bằng các sử dụng mạng lưới Nơ-ron nhân tạo (**_Neuron Network_**). Các mạng lưới này giúp tìm ra các biểu hiện cần thiết để phát hiện hoặc phân loại tối tượng cần tìm.
    - Image recognition (_Google Photos, Facebook facial recognition,..._)
    - Voice assistants (_Siri, Alexa,..._)
    - Language translation (_Google Translate,..._)
    - ...
  - **Natural Language Processing** (NLP): Nhánh của AI tập trung vào việc cho phép máy tính hiểu, diễn giải, tạo ra và thao tác ngôn ngữ con người một cách hiệu quả.
    - Chatbots (Chat GPT, Deepseek, Claude,...)
    - Grammar correction software (_Grammarly,..._)
    - ...
  - **Computer Vision** (CV): Lĩnh vực giúp máy tính rút ra thông tin có ý nghĩa từ hình ảnh kỹ thuật số, video, camera,...
    - Autonomous vehicles
    - Facial recognition systems
    - ...
  - ...

## 3.2. Chuẩn bị Dataset, Environment

> [!NOTE]
>
> Trong quá trình cài đặt trong Buổi này, bản hướng dẫn sử dụng [Conda](https://anaconda.org/) làm trình quản lý môi trường và Sử dụng [Visual Studio Code](https://code.visualstudio.com/) để làm trình Code Editor.

### Chuẩn bị Dataset

- Tải Dataset tại đây: [Kaggle](https://www.kaggle.com/datasets/carlosrunner/pizza-not-pizza)

  - Đăng nhập vào Kaggle

    ![Đăng nhập](Buổi%203%20Ảnh%201.png)

  - Chọn phương thức đăng nhập (Chọn phương án bất kỳ, ở đây chọn Google cho tiện)

    ![Phương thức đăng nhập](Buổi%203%20Ảnh%202.png)

  - Tải về Dataset

    ![Tải về Dataset](Buổi%203%20Ảnh%203.png)

  - Chọn tải "Download Dataset as zip"

    ![Tải về File zip](Buổi%203%20Ảnh%204.png)

### Thiết lập Môi trường

> [!NOTE]
>
> Nếu bạn chưa có Conda thì xem lại [Buổi 1](/Buổi%201/Buổi%201.md)

- Tạo Project và môi trường

  - Tạo một thư mục để chưa Project (Ở đây của mình là `F:\Code\Python\PizzaClassifier`)

    ![Tạo thư mục](Buổi%203%20Ảnh%205.png)

  - Mở Visual Studio Code tại thư mục vừa tạo

    ![Mở thư mục bằng VSCode 1](Buổi%203%20Ảnh%206.png)

    ![Mở thư mục bằng VSCode 2](Buổi%203%20Ảnh%207.png)

  - Mở Terminal trong Visual Studio Code

    ![Mở Terminal trong VSCode 1](Buổi%203%20Ảnh%208.png)

    ![Mở Terminal trong VSCode 2](Buổi%203%20Ảnh%209.png)

  - Tạo môi trường với Python 3.12 (Pytorch chưa hỗ trợ Python 3.13 hiện tại)

    ```
    conda create --name PizzaClassifier python=3.12
    ```

    ![Tạo môi trường](Buổi%203%20Ảnh%2010.gif)

  - Activate Môi trường trước khi cài đặt Pytorch

    ```
    conda activate PizzaClassifier
    ```

    ![Sử dụng môi trường](Buổi%203%20Ảnh%2011.gif)

  - Cài đặt Pytorch có Cuda (Nếu bạn có sử dụng GPU của Nvidia) [Chi tiết➚](https://pytorch.org/#:~:text=and%20easy%20scaling.-,INSTALL%20PYTORCH,-Select%20your%20preferences)

    - Có sử dụng cuda

    ```
    pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu126
    ```

    - Không sử dụng cuda

    ```
    pip3 install torch torchvision torchaudio
    ```

    ![Cài đặt Pytorch](Buổi%203%20Ảnh%2012.gif)

  > [!NOTE]
  >
  > Khuyến khích sử dụng GPU để tăng hiệu suất Training

  - Tạo một file tên bất kỳ (Ở đây là `main.py`) để test Pytorch

    ![Tạo file](Buổi%203%20Ảnh%2013.png)

  - Sử dụng code sau để kiểm tra xem Pytorch có thể sử dụng được GPU không?

    ```python
    import torch

    # Kiểm tra GPU
    device = torch.device("cuda:0" if torch.cuda.is_available() else "cpu")
    print(f"Sử dụng thiết bị: {device}")
    ```

    ![Sử dụng Code](Buổi%203%20Ảnh%2014.png)

  - Chạy thử Code

    ```
    python main.py
    ```

    - Nếu chỉ cài bình thường không có cài Cuda

      ![Test Pytorch 1](Buổi%203%20Ảnh%2015.gif)

    - Nếu có cài Cuda thì kết quả sẽ như này

      ![Test Pytorch 2](Buổi%203%20Ảnh%2016.png)

    > [!NOTE]
    >
    > Nếu lỡ cài bằng lệnh chỉ cho CPU thì cài bài có GPU bằng cách gỡ `torch` `torchvision` `torchaudio` bằng lệnh:
    >
    > ```
    > pip3 uninstall torch torchvision torchaudio
    > ```
    >
    > Sau đó dùng lệnh cài đặt có GPU như bình thường
    >
    > ```
    > pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu126
    > ```
