
### Thông tin
- Chuẩn bị: 0.001 ETH ~1$ - 2$ trên Eclipse mainnet
- Ví backpack


### Cấu hình tối thiểu
- CPU 1 Core
- Ram 1 GB
- Ổ cứng SSD 20 GB
- Hệ điều hành linux Ubuntu 24.04

### Code chạy

1. Update

```
sudo apt-get update && sudo apt-get upgrade -y
```

```
sudo apt install screen curl nano  -y
```

2. Cài Rust
```
 curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

```
source $HOME/.cargo/env
```

3. Cài đặt Solana CLI
```
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```

Kiểm tra version

```
solana version
```

Note: Nếu lỗi không tìm thấy version thì cài lệnh bên dưới

```
echo 'export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
````


Kiểm tra lại

```
solana version
```

4. tạo ví

```
solana-keygen new
```
- Tiếp tục đặt mật khẩu & Lưu lại mnemonic

5. Cài đặt Bitz CLI
```
cargo install bitz
```

6. Cài đặt RPC

Chọn RPC nào chạy ngon nhất

```
solana config set --url https://mainnetbeta-rpc.eclipse.xyz/
```

hoặc

```
solana config set --url https://eclipse.helius-rpc.com/
```

Hoặc (mình đang dùng cái này mới cập nhật khá ổn)

```
solana config set --url https://bitz-000.eclipserpc.xyz/
```

7. Lấy private key (là nguyên cái dãy số) & Import vào ví Backpack
```
cat ~/.config/solana/id.json
```

- Nạp tiền vào địa chỉ ví đã import
- Nạp khoảng 0.0005 ETH là đủ nhưng bạn có thể nạp khoảng 5 - 10$ khoảng 0.005 - 0.007 ETH
- có thể dùng cầu relay.link/bridge

8. Chạy miner
```
screen -S bitz
```
```
bitz collect
```


MỘT SỐ LỆNH TIỆN ÍCH

- Lệnh xem tài khoản:
```
bitz account
```

- Lệnh claim $BITZ từ node về ví
```
bitz claim
```

- Tuỳ chọn chạy số core CPU theo ý muốn:
```
bitz collect --cores <số core cpu>
```

