# CodeIgniter-Weixin_Library
即插即用微信网页授权模块, 适用于[CodeIgniter](https://github.com/bcit-ci/CodeIgniter)框架

## 起步
该模块为即插即用模块, 只需`clone`该项目即可开始使用

### 目录结构
```
CodeIgniter-Weixin_Library/
├── config/
│   └── wx_library.php
├── libraries/
│   └── Wx_library.php
└── third_party/
    └── weixin/
        └── ...
```

### 安装
将项目中的:
- `config/wx_library.php`文件放入你的项目中`application/config/`目录
- `libraries/Wx_library.php`文件放入你的项目中`application/libraries/`目录
- `third_party/weixin/`目录放入你的项目中`application/third_party/`目录


## 加载和使用

### 配置
修改`wx_library.php`配置文件, 填入所开发公众号的信息:
```
<?php
/**
 * 微信公众号配置
 */
$config = array(
    'appid'  => '', // 必填
    'secret' => '', // 必填
    'token'  => '',
);
```

### 加载
在你的`controller`中, 使用`$this->load->library()`来加载该库
```
// controller
// (建议将别名设为`wx`)
$this->load->library('Wx_library', null, 'wx')
```

### API
`Wx_library`提供2个API:
```
// 发起微信授权登录
$this->wx->login();

// 返回微信 js sdk 配置选项 signPackage
$this-wx->signPackage();
```

## License
MIT License. Check the `LICENSE` file.