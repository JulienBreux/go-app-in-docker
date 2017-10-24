# BUILD: docker build --no-cache --rm -t temp/solution:4 .
# RUN:   docker run --rm temp/solution:4

FROM golang:1-alpine as builder
WORKDIR /go/src/github.com/JulienBreux/go-program-in-docker/
RUN apk --update add ca-certificates
COPY main.go .
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app .

FROM scratch
ENV PATH=/bin
WORKDIR /root/
COPY --from=builder /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/ca-certificates.crt
COPY --from=builder /go/src/github.com/JulienBreux/go-program-in-docker/app .
CMD ["./app"]
