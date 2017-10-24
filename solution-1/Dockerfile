# BUILD: docker build --no-cache --rm -t temp/solution:1 .
# RUN:   docker run --rm temp/solution:1

FROM golang:1

WORKDIR /go/src/app

COPY . .

RUN go build -o app

CMD ["./app"]
