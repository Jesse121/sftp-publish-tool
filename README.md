一键发布的工具

### 如何使用

1. 安装依赖

```
npm install sftp-publish-tool --save-dev
```

2. 在项目文件夹中添加 sftp.config.json 文件，主要内容是要发布的机器及位置，例如：

```
	"dev": {
		"localPath": "./op",
		"remotePath": "/ssd0/webapps/op",
		"protectedRemotePath": "/ssd0/webapps/op",
		"connect": {
			"host": "192.168.xxx.xxx",
			"port": 22,
			"username": "xxx",
			"password": "xxx"
		}
	},
	"test": {
		"localPath": "./op",
		"remotePath": "/data/ssd0/webapps/op",
		"protectedRemotePath": "/data/ssd0/webapps/op",
		"connect": {
			"host": "192.168.xxx.xxx",
			"port": 22,
			"username": "xxx",
			"password": "xxx"
		}
	}
```

3. 在项目 package.json 文件中增加发布命令，例如

```
"publish:dev": "sftp-publish-tool -c op -e dev",
"publish:test": "sftp-publish-tool -c op -e test"
```

参数说明：
-c copy 要复制的文件夹
-e environment 要发布的环境
