工作环境说明
===========

# 目录结构

```
data                                  数据
  └─ backup
  └─ mongodb
  └─ redis
  └─ couchdb
      └─ stackedit                    存储 Stackedit 文章

vxuepai
  └─ api                              API 服务器
  └─ pub
      └─ web                          浏览器
      └─ app
          └─ phone                    手机
          └─ pad                      平板
          └─ tv                       电视
      └─ admin                        管理后台
      └─ ppt                          项目及融资演示
      └─ oss                          图片、视频、音频、课件等
      └─ cdn                          js css img

xlab
  └─ docker                           docker 容器配置
  └─ cattle                           老牛，网络内容抓取库
  └─ fakery                           虚拟数据生成器

```

# 网盘路径

```
/mnt
  └─ b                                系统赠送的20G，用于抓取内容暂存
      └─ crawler
  └─ hgfs                             自购的30G
      └─ ftp
      └─ workspace
  └─ hub                              独立网盘5G
      └─ repos
```

# 环境配置

1. **ftp** - 端口 **21** - 目录 ``/mnt/hgfs/ftp``
> ``docker run -d -p 21:21 -v /mnt/hgfs/ftp:/var/ftp --name ftp beetaa/vsftpd``

2. **mongodb** - 端口 **27017** - 目录 ``/mnt/hgfs/workspace/data/mongodb``
> ``docker run -d -p 27017:27017 -v /mnt/hgfs/workspace/data/mongodb:/data/db --name mongodb mongo:latest --logpath /data/db/mongodb.log --logappend``

3. **redis** - 端口 **6379** - 目录 ``/mnt/hgfs/workspace/data/redis``
> ``docker run -d -p 6379:6379 -v /mnt/hgfs/workspace/data/redis:/data --name redis redis``

4. **couchdb** - 端口 **5984** | **6984** - 目录 ``/mnt/hgfs/workspace/data/couchdb`` 和 ``/mnt/hgfs/workspace/data/couchdb/log``
> ``docker run -d -p 5984:5984 -p 6984:6984 -v /mnt/hgfs/workspace/data/couchdb:/usr/local/var/lib/couchdb -v /mnt/hgfs/workspace/data/couchdb/log:/usr/local/var/log/couchdb --name couchdb beetaa/couchdb``

5. **coming soon 页面** - 端口 **80** - 目录 ``/mnt/hgfs/workspace/vxuepai/pub/web/_coming``
> ``docker run -d -p 80:80 -v /mnt/hgfs/workspace/vxuepai/pub/web/_coming:/usr/share/nginx/html --name coming nginx``

6. **OSS 存储** - 端口 **8011** - 目录 ``/mnt/hgfs/workspace/vxuepai/pub/oss``
> ``docker run -d -p 8011:80 -v /mnt/hgfs/workspace/vxuepai/pub/oss:/usr/share/nginx/html --name oss nginx``

7. **CDN 静态文件服务** - 端口 **8022** - 目录 ``/mnt/hgfs/workspace/vxuepai/pub/cdn``
> ``docker run -d -p 8022:80 -v /mnt/hgfs/workspace/vxuepai/pub/cdn:/usr/share/nginx/html --name cdn nginx``

6. **cloud9** - 端口 **8181** - 目录 ``/mnt/hgfs/workspace/vxuepai``
> ``docker run -d -p 8181:8181 -v /mnt/hgfs/workspace/vxuepai:/workspace --name cloud9 beetaa/cloud9``