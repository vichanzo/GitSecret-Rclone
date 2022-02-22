

```
apk add rclone fuse
```

```
rclone config
# Choose 23 (OneDrive)

rclone --vfs-cache-mode writes mount onedrive-vc:/ ./downloads
```
