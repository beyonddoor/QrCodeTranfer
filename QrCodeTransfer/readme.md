# QrTransfer

## What is QrTransfer?

QrTransfer trys to make it easy to transfer files without display devices only.

## Install

Install python modules

```sh
pip3 install pypng
pip3 install pillow
pip3 install PyQt5
pip3 install pyzbar
pip3 install pyqrcode
```

Install `zbar`

```sh
brew install zbar
```

```py
import pyqrcode
qr = pyqrcode.create("HORN O.K. PLEASE.")
qr.png("horn.png", scale=6)

import qrtools
qr = qrtools.QR()
qr.decode("horn.png")
print(qr.data)
```

## TODO

- [x] add command channel. `> command line`
  - [ ] 命令协商wait的时间，截屏的大小等
- [ ] receiver: add new threads to processing QR scanning, and wait quit signal in console.
- [ ] 尝试更高效的传输方式，压缩，qr的版本（iqr？），屏幕显示qr的数量
- [ ] 性能优化
  - [ ] sender：生成的qr图片保存在内存中
