FROM golang:latest

# 作業ディレクトリを設定
WORKDIR /app

# モジュールファイルを先にコピーして、キャッシュを活用
COPY go.mod go.sum ./
RUN go mod download

# ソースコードをコピー
COPY . .

# airインストール（ホットリロード用）
RUN go install github.com/air-verse/air@latest

# ポートを公開
EXPOSE 8080

# airでアプリケーションを実行（ソースコード変更を監視）
CMD ["air"]