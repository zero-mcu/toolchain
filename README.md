# toolchain

## 安装USB 设备库
```
sudo apt-get install libusb-1.0-0-dev
```

## 下载安装最新的ST-Link utilites
```
git clone https://github.com/ArnoYuan/stlink.git
cd stlink
make build
cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make install
sudo cp libstlink* /usr/lib
cd ..
#install udev rules
sudo cp etc/udev/rules.d/49-stlinkv* /etc/udev/rules.d/
#and restart udev
sudo udevadm control --reload
```

## 下载代码到板卡
```
st-flash write xxx.bin 0x8000000
```

## 使用GDB调试
```
# 启动gdb 服务
st-util

# 使用gcc gdb加载elf文件
arm-none-eabi-gdb test.elf

```


