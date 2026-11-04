# Qiniu Cloud SDK for PHP（aoding9 fork）

> 基于 [qiniu/php-sdk](https://github.com/qiniu/php-sdk) 的维护 fork：修复 PHP 8.4+ 隐式 nullable 等兼容问题，已在 **PHP 8.5** 验证。通过 `replace` 可替代官方 `qiniu/php-sdk`。

[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](LICENSE)
[![Latest Stable Version](https://img.shields.io/packagist/v/aoding9/qiniu-php-sdk.svg)](https://packagist.org/packages/aoding9/qiniu-php-sdk)
[![Total Downloads](https://img.shields.io/packagist/dt/aoding9/qiniu-php-sdk.svg)](https://packagist.org/packages/aoding9/qiniu-php-sdk)
<img src="https://img.shields.io/badge/PHP-%3E%3D7.1%20(incl.%208.5)-59a9f8.svg?style=flat" />

## 安装

```bash
$ composer require aoding9/qiniu-php-sdk
```

## 运行环境

| Qiniu SDK版本 | PHP 版本 |
|:--------------------:|:-----------------------------------------------:|
| 7.x（本 fork） | cURL extension，`composer.json` 约束 `>=7.1`，含 **7.1–8.5** |
| 官方 7.x | cURL extension，约 5.3–5.6、7.0–7.4、8.0–8.1 |
| 6.x | cURL extension，5.2–5.6 |

## 使用方法

### 上传
```php
use Qiniu\Storage\UploadManager;
use Qiniu\Auth;
...
    $uploadMgr = new UploadManager();
    $auth = new Auth($accessKey, $secretKey);
    $token = $auth->uploadToken($bucket);
    list($ret, $error) = $uploadMgr->putFile($token, 'key', 'filePath');
...
```

## 测试

``` bash
$ ./vendor/bin/phpunit tests/Qiniu/Tests/
```

## 常见问题

- `$error` 保留了请求响应的信息，失败情况下 `ret` 为 `none`, 将 `$error` 可以打印出来，提交给我们。
- API 的使用 demo 可以参考 [examples](https://github.com/qiniu/php-sdk/tree/master/examples)。

## 代码贡献

详情参考[代码提交指南](https://github.com/qiniu/php-sdk/blob/master/CONTRIBUTING.md)。

## 贡献记录

- [所有贡献者](https://github.com/qiniu/php-sdk/contributors)

## 联系我们

- 如果需要帮助，请提交工单（在portal右侧点击咨询和建议提交工单，或者直接向 support@qiniu.com 发送邮件）
- 如果有什么问题，可以到问答社区提问，[问答社区](https://qiniu.segmentfault.com/)
- 更详细的文档，见[官方文档站](https://developer.qiniu.com/)
- 如果发现了 bug， 欢迎提交 [issue](https://github.com/qiniu/php-sdk/issues)
- 如果有功能需求，欢迎提交 [issue](https://github.com/qiniu/php-sdk/issues)
- 如果要提交代码，欢迎提交 pull request
- 欢迎关注我们的[微信](https://www.qiniu.com/#weixin) [微博](https://weibo.com/qiniutek)，及时获取动态信息。

## 代码许可

The MIT License (MIT).详情见 [License文件](https://github.com/qiniu/php-sdk/blob/master/LICENSE).

[packagist]: http://packagist.org
[install-packagist]: https://packagist.org/packages/aoding9/qiniu-php-sdk
