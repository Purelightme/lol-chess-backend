### lol云顶之弈助手后端代码
- 开始日期：2019-08-20

# 项目概述
 - 产品名称：云顶之弈助手
 - 测试地址：[云顶之弈助手后台](http://shop.bettertaro.com/admin)

# 功能如下
- 
- 
- 
- 
- 

# 运行环境要求
- nginx
- php7.0+
- mysql5.7
- beanstalkd(queue work driver)

# 开发环境部署/安装
本项目代码使用PHP框架Laravel5.5开发，本地开发环境使用laradock。

## 基础安装

#### 1，克隆代码库
```git clone http://code.bettertaro.com:10080/purelightme/shop.git```

#### 2，配置虚拟域名
请参考：[laradock](http://laradock.io)

#### 3，安装依赖
```composer install```

#### 4，生成配置文件
```cp .env-example .env```
你可以根据情况修改.env文件里面的内容，如数据库连接等。

#### 5，生成数据表及测试数据
```php artisan migrate --seed```

#### 6，生成秘钥
```php artisan key:generate```

#### 7，生成passport客户端
```php artisan passport:install```

#### 8，运行队列监听器
```
工具随意，可以不用supervisord，例如pm2（基于nodejs）

sudo cp shop.supervisor.conf /etc/supervisor/conf.d

sudo supervisorctl reread

sudo supervisorctl update

sudo supervisorctl start dcd:*
```

#### 10，配置hosts
```echo "127.0.0.1   shop.test" | sudo tee -a /etc/hosts```

## 链接入口
- 管理后台：[后台管理](http://shop.test/admin)

至此，安装完成^_^。

# 生产环境部署
- 推荐使用 [deployer](http://deployer.org)
- ```dep deploy scl```

## 补充说明
  - 修改php.ini配置
  ```php
  post_max_size=30M
  upload_max_filesize=20M
  ```
