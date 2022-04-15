# Dockerの利用
## GitHubから取得
- cloneする  
`$ git clone git@github.com:adya2523/docker-anaconda.git`

- cloneしたディレクトリに移動

- Dockerイメージの作成  
`$ docker build -t <image_name>`
  - `<image_name>`：Dockerイメージの名前（REPOSITORY:tag）を指定
  

- Dockerコンテナの起動  
`$ docker run -d -p 8888:8888 -v C:\git\docker-anaconda\work:/work --name <container_name> <image_name>`  
  - `-p <port>:8888`：ホストに紐づけるポートを指定
  - `-v <host_dir>:<container_dir>`：マウントするホストのディレクトリとコンテナのディレクトリを指定
    - 例）Mac：`~/Desktop/ds_python:/work`
  - `<container_name>`：Dockerコンテナの名前を指定


## Docker hubから取得
- 以下のリポジトリから取得  
https://hub.docker.com/repository/docker/adya2523/anaconda  
`$ docker pu adya2523/anaconda`

- Dockerコンテナの起動  
`$ docker run -d -p 8888:8888 -v C:\git\docker-anaconda\work:/work --name <container_name> <image_name>`  
  - `-p <port>:8888`：ホストに紐づけるポートを指定
  - `-v <host_dir>:<container_dir>`：マウントするホストのディレクトリとコンテナのディレクトリを指定
    - 例）Mac：`~/Desktop/ds_python:/work`
  - `<container_name>`：Dockerコンテナの名前を指定


# （参考）Docker hubにpush
- Dockerhubにリポジトリ作成  
例）`adya2523/docker-anaconda`

- Dockerfileのあるディレクトリに移動

- Dockerイメージ作成  
例) `$ docker build -t adya2523/docker-anaconda . `

- Dockerhubにpush  
例）`$ docker push adya2523/docker-anaconda`
