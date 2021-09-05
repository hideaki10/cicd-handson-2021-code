# ベースイメージ指定
FROM golang:1.16 as builder

# ワークディレクトリを指定
WORKDIR /app

# ホストOSのapps内全てをWORKDIRにコピー
COPY . ./

# ビルド
RUN go build -o ./server-run ./server

# [追加] 軽量なdistrolessイメージを指定
FROM gcr.io/distroless/base

# コンテナのポートを9090で公開
EXPOSE 9090

# アプリ実行
CMD [ "./server-run" ]