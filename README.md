<p align="center">
  <a href="https://github.com/whyour/qinglong">
    <img width="150" src="https://qinglong.whyour.cn/qinglong.png">
  </a>
</p>

<h1 align="center">青龙(WIP)</h1>

<div align="center">

Python 和 JavaScript 定时任务管理面板

[![docker version][docker-version-image]][docker-version-url] [![docker pulls][docker-pulls-image]][docker-pulls-url] [![docker stars][docker-stars-image]][docker-stars-url] [![docker image size][docker-image-size-image]][docker-image-size-url] [![donate][donate-image]][donate-url]

[donate-image]: https://img.shields.io/badge/donate-wechat-green?style=flat
[donate-url]: https://qinglong.whyour.cn/nice.png
[docker-pulls-image]: https://img.shields.io/docker/pulls/whyour/qinglong?style=flat
[docker-pulls-url]: https://hub.docker.com/r/whyour/qinglong
[docker-version-image]: https://img.shields.io/docker/v/whyour/qinglong?style=flat
[docker-version-url]: https://hub.docker.com/r/whyour/qinglong/tags?page=1&ordering=last_updated
[docker-stars-image]: https://img.shields.io/docker/stars/whyour/qinglong?style=flat
[docker-stars-url]: https://hub.docker.com/r/whyour/qinglong
[docker-image-size-image]: https://img.shields.io/docker/image-size/whyour/qinglong?style=flat
[docker-image-size-url]: https://hub.docker.com/r/whyour/qinglong
</div>

<p align="center">
  <img width="49%" src="https://qinglong.whyour.cn/login.png">
  <img width="49%" src="https://qinglong.whyour.cn/home.png">
</p>

青龙，又名苍龙，在中国传统文化中是四象之一、[天之四灵](https://zh.wikipedia.org/wiki/%E5%A4%A9%E4%B9%8B%E5%9B%9B%E7%81%B5)之一，根据五行学说，它是代表东方的灵兽，为青色的龙，五行属木，代表的季节是春季，八卦主震。苍龙与应龙一样，都是身具羽翼。《张果星宗》称“又有辅翼，方为真龙”。

《后汉书·律历志下》记载：日周于天，一寒一暑，四时备成，万物毕改，摄提迁次，青龙移辰，谓之岁。

在中国[二十八宿](https://zh.wikipedia.org/wiki/%E4%BA%8C%E5%8D%81%E5%85%AB%E5%AE%BF)中，青龙是东方七宿（角、亢、氐、房、心、尾、箕）的总称。 在早期星宿信仰中，祂是最尊贵的天神。 但被道教信仰吸纳入其神系后，神格大跌，道教将其称为“孟章”，在不同的道经中有“帝君”、“圣将”、“神将”和“捕鬼将”等称呼，与白虎监兵神君一起，是道教的护卫天神。

## 安装

### 创建 docker-compose.yml 文件并启动容器

```yml
version: "3"

services:
  qinglong:
    container_name: qinglong
    image: tingv/qinglong:2.2.0
    volumes:
      - $PWD/config:/ql/config
      - $PWD/log:/ql/log
      - $PWD/db:/ql/db
    network_mode: host
    restart: always
```

启动容器:

```shell
docker-compose up -d
```

### 安装并启动 Telegram 机器人

```shell
docker exec -it qinglong ql bot
```

### 设置 Telegram 机器人

路径: `config/bot.json`

### 登录面板并设置

地址: `http://IP:5700`
帐号: `admin`
密码: `adminadmin`

### 拉取脚本仓库

```shell
docker exec -it qinglong ql repo https://github.com/JDHelloWorld/jd_scripts.git "jd_|jx_|getJDCookie" "activity|backUp|jd_delCoupon" "^jd[^_]|USER"
docker exec -it qinglong ql repo https://github.com/panghu999/jd_scripts.git "jd_|jx_|getJDCookie" "activity|backUp|jd_delCoupon|format_" "^jd[^_]|USER"
docker exec -it qinglong ql repo https://github.com/chinnkarahoi/jd_scripts.git "jd_|jx_|getJDCookie" "activity|backUp|jd_delCoupon" "^jd[^_]|USER"
docker exec -it qinglong ql repo https://github.com/he1pu/JDHelp.git "jd_|jx_|getJDCookie" "activity|backUp|jd_delCoupon" "^jd[^_]|USER"
```

### 面板内添加定时更新脚本仓库

## 其他命令

```shell
docker exec -it qinglong bash   # 进入容器
```


## 多谢

* [nevinee](https://gitee.com/evine)

* [crontab-ui](https://github.com/alseambusher/crontab-ui)

* [Ant Design](https://ant.design)

* [Ant Design Pro](https://pro.ant.design/)

* [Umijs3.0](https://umijs.org)

* [darkreader](https://github.com/darkreader/darkreader)
