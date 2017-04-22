# Yowsup 2 [![Build Status](https://travis-ci.org/tgalal/yowsup.svg?branch=master)](https://travis-ci.org/tgalal/yowsup) [![Join the chat at https://gitter.im/tgalal/yowsup](https://badges.gitter.im/tgalal/yowsup.svg)](https://gitter.im/tgalal/yowsup?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

<a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=Z9KKEUVYEY6BN" target="_blank"><img src="https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif" /></a>

## Updates (March 23, 2017)
Yowsup v2.5.2 is out, See [release notes](https://github.com/tgalal/yowsup/releases/tag/v2.5.2)

==========================================================

## Yowsup opened WhatsApp service under platforms!

Yowsup is a python library that enables you build application which use WhatsApp service. Yowsup has been used to create an unofficial WhatsApp client Nokia N9 through the Wazapp project which was in use by 200K + users as well as another fully featured unofficial client for Blackberry 10

## Quickstart

 * **[yowsup's architecture](https://github.com/tgalal/yowsup/wiki/Architecture)**
 * **[Create a sample app](https://github.com/tgalal/yowsup/wiki/Sample-Application)**
 * **[yowsup-cli](https://github.com/tgalal/yowsup/wiki/yowsup-cli-2.0)**
 * **[Yowsup development, debugging, maintainance and sanity](https://github.com/tgalal/yowsup/wiki/Yowsup-development,-debugging,-maintainance-and-sanity)**

## Installation

 - Requires python2.6+, or python3.0 +
 - Required python packages: python-dateutil,
 - Required python packages for end-to-end encryption: protobuf, pycrypto, python-axolotl-curve25519
 - Required python packages for yowsup-cli: argparse, readline (or pyreadline for windows), pillow (for sending images)

Install using setup.py to pull all python dependencies, or using pip:

```
pip install yowsup2
```

### Linux

You need to have installed python headers (from probably python-dev package) and ncurses-dev, then run
```
python setup.py install
```
Because of a bug with python-dateutil package you might get permission error for some dateutil file called requires.txt when you use yowsup (see [this bug report](https://bugs.launchpad.net/dateutil/+bug/1243202)) to fix you'll need to chmod 644 that file.

### FreeBSD (*BSD)
You need to have installed: py27-pip-7.1.2(+), py27-sqlite3-2.7.11_7(+), then run
```
pip install yowsup2
```

### Mac
```
python setup.py install
```
Administrators privileges might be required, if so then run with 'sudo'

### Windows

 - Install [mingw](http://www.mingw.org/) compiler
 - Add mingw to your PATH
 - In PYTHONPATH\Lib\distutils create a file called distutils.cfg and add these lines:

```
[build]
compiler=mingw32
```
 - Install gcc: ```mingw-get.exe install gcc```
 - Install [zlib](http://www.zlib.net/)
 - ```python setup.py install```

If pycrypto fails to install with some "chmod error". You can install it separately using something like
```easy_install http://www.voidspace.org.uk/downloads/pycrypto26/pycrypto-2.6.win32-py2.7.exe```

or for python3 from:

 > [https://github.com/axper/python3-pycrypto-windows-installer](https://github.com/axper/python3-pycrypto-windows-installer)

and then rerun the install command again

# Special thanks

Special thanks to:

- [CODeRUS](https://github.com/CODeRUS)
- [mgp25](https://github.com/mgp25)
- [SikiFn](https://github.com/SikiFn)
- [0xTryCatch](https://github.com/0xTryCatch)
- [shirioko](https://github.com/shirioko)

and everyone else on the [WhatsAPI](https://github.com/mgp25/WhatsAPI-Official) project for their contributions to yowsup and the amazing effort they put into WhatsAPI, the PHP WhatsApp library

Special thanks goes to all other people who use and contribute to the library as well.

Please **[read this](https://github.com/tgalal/yowsup/wiki/Yowsup-development,-debugging,-maintainance-and-sanity)** if you'd like to contribute to yowsup 2.0

Thanks!


# License:

As of January 1, 2015 yowsup is licensed under the GPLv3+: http://www.gnu.org/licenses/gpl-3.0.html.
=======
# WhatsAppy
WhatsApp Python - forked from https://github.com/tgalal/yowsup

Added recieve downloadable image, document, audio & video message forked from https://github.com/jlguardi/yowsup

Main Features: send text message, image (done), audio (done), video (done), document (on progress)

Example run yowsup in your terminal:

yowsup-cli demos --yowsup --login 6281320203981:NDkxNTIyNTI1NjAyMkBzLndoYXRzYXBwLm5ldA==

to run yowsup as microservice please see https://github.com/EliasKotlyar/yowsup-microservice

Command to broadcast image with caption:

/bcimage send texfile.txt '/tmp/image.jpg' 'Caption Image'

Example textfile.txt:
```
6281223132131
6287231310313
6289692028382
```

## yowsup-cli

yowsup-cli is a command line interface to Yowsup library. It provides you with the options of registration, and provides a few demos such as a command line client

```
$ yowsup-cli

Available commands:
===================
demos, registration, version
```

### yowsup-cli registration

```
$ yowsup-cli registration --help

usage: registration [-h] [-v] [-d] [--help-config] [-c CONFIG] [-m MCC]
                    [-n MNC] [-p PHONE] [-C CC] [-r (sms|voice)] [-R code]

WhatsApp Registration options

optional arguments:
  -h, --help            show this help message and exit
  -v, --version         Print version info and exit
  -d, --debug           Show debug messages
  --help-config         Prints a config file sample

Configuration options:
  Config file is optional. Other configuration arguments have higher
  priority if given, and will override those specified in the config file

  -c CONFIG, --config CONFIG
                        Path to config file. If this is not set then you must
                        set at least --phone and --cc arguments
  -m MCC, --mcc MCC     Mobile Country Code. Check your mcc here:
                        https://en.wikipedia.org/wiki/Mobile_country_code
  -n MNC, --mnc MNC     Mobile Network Code. Check your mnc from
                        https://en.wikipedia.org/wiki/Mobile_country_code
  -p PHONE, --phone PHONE
                        Your full phone number including the country code you
                        defined in 'cc', without preceeding '+' or '00'
  -C CC, --cc CC        Country code. See http://www.ipipi.com/help/telephone-
                        country-codes.htm. This is now required

Modes:
  -r (sms|voice), --requestcode (sms|voice)
                        Request the digit registration code from Whatsapp.
  -R code, --register code
                        Register account on Whatsapp using the code you
                        previously received

```


WhatsApp registration involves 2 steps. First you need to request a registration code. And then you resume the registration with code you got.

Example:

```
yowsup-cli registration --requestcode sms --phone 49XXXXXXXX --cc 49 --mcc 123 --mnc 456
yowsup-cli registration --register 123456 --phone 49XXXXXXXX --cc 49  
```


###yowsup-cli demos
```
$ yowsup-cli demos --help

usage: demos [-h] [-v] [-d] [--help-config] [-l phone:b64password] [-c CONFIG]
             [-m] [-y] [-e] [-s phone message]

Run a yowsup demo

optional arguments:
  -h, --help            show this help message and exit
  -v, --version         Print version info and exit
  -d, --debug           Show debug messages
  --help-config         Prints a config file sample

Configuration options for demos:
  -l phone:b64password, --login phone:b64password
                        WhatsApp login credentials, in the format
                        phonenumber:password, where password is base64
                        encoded.
  -c CONFIG, --config CONFIG
                        Path to config file containing authentication info.
                        For more info about config format use --help-config
  -m, --moxie           Enable experimental support for the new WhatsApp
                        encryption

Command line interface demo:
  -y, --yowsup          Start the Yowsup command line client

Echo client demo:
  -e, --echo            Start the Yowsup Echo client

Send client demo:
  -s phone message, --send phone message
                        Send a message to specified phone number, wait for
                        server receipt and exit
```

Explore the demos yourself ;)
Feel free to implement and send me more demos to include in yowsup-cli
