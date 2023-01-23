
QR code using python 



## Installation

Install Libraries required 

```bash
  pip install qr code 
  pip install PIL
```
A standard install uses pypng to generate PNG files and can also render QR codes directly to the console. A standard install is just:
    
    pip install qrcode 

For more image functionality, install qrcode with the pil dependency so that pillow is installed and can be used for generating images:

    pip install PIL

## What is a QR code ?
It is a machine-scannable image that can instantly be read using a Smartphone camera. Every QR code consists of a number of black squares and dots which represent certain pieces of information. When your Smartphone scans this code, it translate that information into something that can be easily understand by humans.


## Usage

From the command line, use the installed qr script:

    qr = qrcode.QRCode()

Or in Python, use the make shortcut function:

    import qrcode as qr
    img = qr.make("some data here")
    type(img)
    img.save(qrcode.png)

## Advance Usage 
For more control use the QRCode class.For example:

    import qrcode
    qr = qrcode.QRCode(version=1,
                  error_correction=qrcode.constants.ERROR_CORRECT_H,
                  box_size=4,
                   border=5,)

      qr.add_data("some data here")
      qr.make(fit=True)
      img = qr.make_image(fill_color="red",back_color="purple")
      img.save("advqr.png")

The version parameter is an integer from 1 to 40 that controls the size of the QR Code (the smallest, version 1, is a 21x21 matrix). Set to None and use the fit parameter when making the code to determine this automatically.

fill_color and back_color can change the background and the painting color of the QR, when using the default image factory. Both parameters accept RGB color tuples.

The error_correction parameter controls the error correction used for the QR Code. The following four constants are made available on the qrcode package:

ERROR_CORRECT_L
About 7% or less errors can be corrected.
ERROR_CORRECT_M (default)
About 15% or less errors can be corrected.
ERROR_CORRECT_Q
About 25% or less errors can be corrected.
ERROR_CORRECT_H.
About 30% or less errors can be corrected.
The box_size parameter controls how many pixels each "box" of the QR code is.

The border parameter controls how many boxes thick the border should be (the default is 4, which is the minimum according to the specs).