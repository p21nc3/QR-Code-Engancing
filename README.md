# ![alt text][lock] QR Code Enhancing - Major Project [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/skewthreads/QR-secret-sharing/blob/master/LICENSE)

Team Members                       |                    
:---------------------------------:|
Prince Bhardwaj(RA2011008020062)   
Shubham Agrawal(RA2011008020095)
Aniket Srivatsava(RA2011008020097)

Guide               |
:-------------------:|
| Dr. Rajeswari Mukesh| 

![alt text][flow]

## Description
Create QR codes to secret share a message using [Shamir's secret sharing algorithm](https://dl.acm.org/citation.cfm?id=359176). Ideal for cryptocurrency wallet recovery keys, passwords, etc. Protect your message by sharing it to secrets. Print the created QR codes and store them separately somewhere safe.

Shares are not parts of the message. Each share does not reveal any information about the initial message itself. Restoring the initial message needs all shares combined, or a specified minimum amount (default threshold is equal to the number of shares). 

## Demonstration

### Sharing
`python share.py`



Share 1           | Share 2           | Share 3
:------------------:|:-------------------:|:-------------------:
![](./images/1.png) | ![](./images/2.png) | ![](./images/3.png)

### Recovering
`python recover.py`

## Installation

```
git clone https://github.com/skewthreads/QR-secret-sharing.git
cd QR-secret-sharing
pip install -r ./requirements.txt
```

## Suggested Usage
Suggested usage is to create 3 or more shares of your message, print the corresponding QR codes and store them in separate physical locations. In case you need to recover your original message, scan the qr codes, and input the shares in the recovery script.

You can specify the number of shares that will be sufficient to recover the original message. This threshold must obviously be greater than 2. The most secure practice is to set that threshold equal to the number of shares. If you set it to a number less than the number of shares, then you can recover your secret using less shares. For example, you can split your message into 4 shares and set your recovering threshold to 3, you can get the original message using any 3 of the 4 shares, in case that a share gets destroyed. But beware, an adversary can recover your secret using only 3 shares as well. Use this security/usability trade-off with caution.

## Modules Imported
- [inquirer](https://github.com/magmax/python-inquirer)
- [secretsharing](https://github.com/blockstack/secret-sharing)
- [PyQRCode](https://github.com/mnooner256/pyqrcode)
- [pypng](https://github.com/drj11/pypng)
- [animation](https://github.com/bprinty/animation)


[lock]: ./images/lock-small.png

[flow]: ./images/QR-Secret-Sharing-flow.png

