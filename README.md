# Tools
```shell
# 安装工具
go install github.com/air-verse/air@latest
```

项目根目录下创建 `.air.toml` 文件，`.air.toml` 基于 air_example.toml 文件修改了以下参数配置：
```conf
# air在运行时存储临时文件的目录
tmp_dir = "/tmp/air"
 
[build]
# cmd 指定了监听文件有变化时，air 需要执行的命令。
# 这里指定了执行构建 opsx-bff 二进制文件, 后期可以使用 make 相关命令替换
cmd = "go build -o _output/opsx-bff -v cmd/opsx-bff/main.go" 
# bin 指定了执行完 cmd 命令后，执行的二进制文件。
# 这里指定了执行 _output/ opsx-bff 文件
bin = "_output/opsx-bff"
# args_bin 指定了运行二进制文件（bin/full_bin）时添加额外参数，这里设置为空
args_bin = []
```
运行：默认使用当前目录下的 .air.toml 配置，你可以通过 `-c` 选项指定配置，例如：`air -c .air.toml`
```shell
#air
running...
2025/10/26 15:49:10 maxprocs: Leaving GOMAXPROCS=16: CPU quota undefined
Hello Opsx BFF!
```