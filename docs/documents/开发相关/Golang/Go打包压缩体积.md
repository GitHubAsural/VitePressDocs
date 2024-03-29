# Go打包压缩体积

> 打包 + 压缩
>
> 1.  将 Go 项目打包为二进制可执行文件时，您可以使用以下技巧来减小二进制文件的大小和压缩体积：
>     1.  使用 `-ldflags="-s -w"` 标志来禁用符号表和调试信息的生成，这可以显著减小二进制文件的大小。
>     2.  对于静态链接库，可以使用 `CGO_ENABLED=0` 环境变量禁用 CGO 并静态编译链接库，这可以减少二进制文件的依赖性和大小。
>         ```bash
>         go build -ldflags "-s -w" -o main
>         ```
>     3.  通过使用 UPX 等工具对二进制文件进行压缩，可以进一步减小二进制文件的大小。例如，您可以使用以下命令对二进制文件进行压缩:
>         ```bash
>         upx --brute <二进制main文件>
>         ```
