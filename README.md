# Pulsar User Manual

[Web Preview](https://pulsar-docs.readthedocs.io/zh_CN/latest/index.html#)

## 1. Project Background

AI toolchain manual public maintenance project

- Provide a unified AI toolchain documentation developer community display address
- Reduce the maintenance cost of AI toolchain Developer
- Reduce AI toolchain User learning cost

## 2. local operation guide

### 2.1 git clone

```bash
git clone https://github.com/AXERA-TECH/pulsar-doc-en.git
```

目录树如下:

```bash
.
├── build
│   ├── doctrees
│   └── html
├── LICENSE
├── make.bat
├── Makefile
├── README.md
├── requirements.txt
└── source                     # Document Body
    ├── conf.py
    ├── examples               # Some examples are saved in .zip format, due to the limitation of git pages, online documents do not support click-to-download operations
    ├── faq
    ├── index.rst
    ├── media
    ├── pulsar
    ├── test_configs
    ├── user_guides_advanced
    ├── user_guides_quick
    └── user_guides_runtime
```

### 2.2 Compile

Installing dependencies

```bash
pip install -r requirements.txt
```

Execute the following command in the project root directory

```bash
$ make clean
$ make html
```

### 2.3 Preview

After compiling, use your browser to view `build/html/index.html` . If you are developing on a server, you can access the compiled files via `ssh` port forwarding as follows:

First, you can use `python` to start an `http` service in the `build/html/` folder after the build,

```bash
$ cd build/html/
$ python -m SimpleHTTPServer 8005  # For python2, Ports can be customized
# or
$ python3 -m http.server 8005      # For python3, Ports can be customized
```

Then link to the server via `ssh`,

``bash
ssh -L 8005:localhost:8005 username@server
```

Then local browser access: ``localhost:8005/index.html``

## 3. Reference

- This project is built on Sphinx, for more information about Sphinx please see https://www.sphinx-doc.org/en/master/

## 4. release


