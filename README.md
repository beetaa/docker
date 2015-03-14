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
  └─ docker
  └─ river
  └─ faker

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