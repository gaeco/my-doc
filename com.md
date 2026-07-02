## Hello
```
mkdir -p /data/labeling/label-studio-data
sudo chown -R 1001:1001 /data/labeling/label-studio-data

docker run -d \
  --name label-studio \
  --restart unless-stopped \
  -p 9080:8080 \
  -v /data/labeling/label-studio-data:/label-studio/data \
  -e LABEL_STUDIO_HOST=http://gpu-server.internal:9080 \
  -e LABEL_STUDIO_VERSION_CHECK=false \
  -e COLLECT_ANALYTICS=false \
  heartexlabs/label-studio:1.23.0

```
