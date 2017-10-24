# BUILD: docker build --no-cache --rm -t temp/solution:2 .
# RUN:   docker run --rm temp/solution:2

FROM golang:1-alpine

WORKDIR /go/src/app

COPY . .

RUN go build -o app

CMD ["./app"]
