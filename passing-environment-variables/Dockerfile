FROM alpine

# ビルドに必要な環境変数はARGを介して受け取る必要があります
ARG MY_VALUE
# 複数ARGを受け取ることも可能です
ARG MY_VALUE2

RUN env
# Output:
# MY_VALUE=hello world!
# MY_VALUE2=goodbye world!

# コンテナ実行時にも環境変数として使いたい場合は、ENV命令とARGの値を用いて、ランタイム環境変数を宣言する必要があります
ENV MY_VALUE=$MY_VALUE
ENV MY_VALUE2=$MY_VALUE2

CMD [ "env" ]
