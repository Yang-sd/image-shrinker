# NAS 部署参考

## 部署信息

| 项目 | 值 |
| --- | --- |
| NAS | `192.168.3.31` |
| SSH 用户 | `deploy` |
| 项目目录 | `/var/services/homes/deploy/project/image-shrinker` |
| 容器名称 | `image-shrinker` |
| 本机监听 | `127.0.0.1:8185` |
| 公网域名 | `image.yangjunhu.com` |
| 线上地址 | `https://image.yangjunhu.com/` |
| 健康检查 | `https://image.yangjunhu.com/healthz` |

## 更新部署

```bash
cd /var/services/homes/deploy/project/image-shrinker
sudo /usr/local/bin/docker-compose up -d --build
sudo /usr/local/bin/docker-compose ps
curl -fsS http://127.0.0.1:8185/healthz
curl -fsS https://image.yangjunhu.com/healthz
```

网页仅提供静态资源，用户选择的图片和视频全部在浏览器内处理，不会上传到 NAS。
