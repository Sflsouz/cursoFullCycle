FROM golang:1.21-rc-alpine3.17 as golang

WORKDIR /go/app
COPY . .
RUN go mod init hello.go
RUN go build -o hello

FROM scratch as final
COPY --from=golang /go/app/hello /hello
CMD ["./hello"]
