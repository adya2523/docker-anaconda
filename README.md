# Dockerの利用
cloneしたフォルダに移動

Dockerイメージの作成
- `<image_name>`：Dockerイメージの名前（REPOSITORY:tag）を指定
`$ docker build -t <image_name>`

Dockerコンテナの起動
- `-p <port>:8888`：ホストに紐づけるポートを指定
- `-v <host_dir>:<container_dir>`：マウントするホストのディレクトリとコンテナのディレクトリを指定
  - 例）Windows：`C:\git\statistics:/work`     
  - 例）Mac：`~/Desktop/ds_python:/work`
- `<container_name>`：Dockerコンテナの名前を指定
`$ docker run -p 8888:8888 -v ~/Desktop/ds_python:/work --name <container_name> <image_name>`

# Docker hubにpush
Dockerhunにリポジトリ作成  
例）`adya2523/docker-anaconda`

Dockerイメージ作成  
例)`$ docker build -t adya2523/docker-anaconda . `

Dockerhubにpush  
例）`$ docker push adya2523/docker-anaconda`
