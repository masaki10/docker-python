## DockerでPythonの環境構築

イメージ作成→コンテナ作成→コンテナ起動
```
cd docker-python
docker compose up -d --build
```

コンテナ起動確認
```
docker container ls
```

コンテナ接続
```
docker compose exec python3 bash
```

hello world
```
cd src 
python sample.py
```

コンテナ停止
```
exit
docker stop python3
```

コンテナ起動（二回目以降）
```
docker compose up -d
```

コンテナ停止 & コンテナ削除
```
docker compose down
```

### Jupyter Notebookを使用する場合
コンテナ内でJupyter Notebook用のサーバーを立ち上げ
```
docker run -v $PWD/src:/root/src -w /root/src -it --rm -p 7777:8888 docker-python_python3 jupyter-lab --ip 0.0.0.0 --allow-root -b localhost
```

http://127.0.0.1:7777 にアクセス
