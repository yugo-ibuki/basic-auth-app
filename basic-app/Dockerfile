# ベースイメージとして公式のGoイメージを使用
FROM golang:1.17-alpine

# 作業ディレクトリを設定
WORKDIR /app

# 依存関係を解決するために、go.modとgo.sumファイルをコピー
COPY go.mod .

# 依存関係をダウンロード
RUN go mod download

# ソースコードをコピー
COPY .. .

# プログラムをビルド
RUN go build -o basic-auth-client main.go

# 8080ポートを公開
EXPOSE 8080

# ビルドしたプログラムを実行
CMD ["./basic-auth-client"]
