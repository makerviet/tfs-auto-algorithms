# Hướng dẫn sử dụng Docker cho Cuộc đua số 2023

Các team cần đóng gói ứng dụng của mình thành môi trường Docker và nộp lại cho BTC:

+ Mã nguồn
+ Dockerfile
+ Hướng dẫn sử dụng (build và chạy mã nguồn).

BTC sẽ sử dụng Docker để chạy ứng dụng của các team.

## Build và chạy Docker mẫu từ BTC:

- Đảm bảo các team đã cài Docker/ Docker Desktop trên máy tính của mình.
- Build Docker và tag lại image theo tên của team mình:

```bash
docker build -t <team_name> .
```

Ví dụ:

```bash
docker build -t team-example .
```

- Chạy code (mở cổng 4567 để điều khiển):

```bash
docker run --gpus all --ipc=host --ulimit memlock=-1 --ulimit stack=67108864 -p 4567:4567 <team_name>
```

Ví dụ:

```bash
docker run --gpus all --ipc=host --ulimit memlock=-1 --ulimit stack=67108864 -p 4567:4567 team-example
```

## Hướng dẫn nộp code:

- Các team thực hiện chuẩn hoá môi trường theo hướng dẫn trên. Trong Dockerfile sử dụng base image là `nvcr.io/nvidia/pytorch:22.12-py3`, và có thể thêm các thư viện cần thiết khác.
- Mã nguồn và tài liệu cài đặt cần gửi về trước ngày 12/08/2023 về BTC.

