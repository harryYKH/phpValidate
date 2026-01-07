# PHP Validate

A standalone, framework-agnostic PHP validation library refactored from ThinkPHP's validator.
这是一个基于 ThinkPHP 框架验证器改造的独立 PHP 验证库，可用于任何 PHP 项目。

## Features / 特性

- **Framework Agnostic / 框架无关**: Can be used in any PHP project (Laravel, Symfony, Slim, plain PHP, etc.).
- **Standalone / 独立**: No dependencies on ThinkPHP core, ORM, or other components.
- **Easy to Use / 简单易用**: Familiar API for ThinkPHP users.

## Requirements / 环境要求

- PHP >= 8.1

## Installation / 安装

```bash
composer require harry-ykh/php-validate
```

## Usage / 使用

```php
use harry\Validate;

$data = [
    'name' => 'harry',
    'email' => 'test@example.com'
];

$validate = new Validate();
$validate->rule([
    'name'  => 'require|max:25',
    'email' => 'email'
]);

if (!$validate->check($data)) {
    var_dump($validate->getError());
}
```

## Removed Features / 移除的特性

Compared to the original ThinkPHP validator, the following dependencies have been removed:
相较于原版 ThinkPHP 验证器，移除了以下依赖：

- **Database Unique Validation / 数据库唯一性验证**: Removed dependency on `think-orm` (`unique` rule).
- **Multi-language Support / 多语言支持**: Removed dependency on `think-lang` (Simplified error messages).
- **Token Validation / 表单令牌**: Removed dependency on `think-session/request` (`token` rule).

## License

Apache-2.0
