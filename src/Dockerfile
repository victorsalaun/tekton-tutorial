FROM golang:1.12 as builder

WORKDIR /go/src/github.com/victorsalaun/tekton-tutorial

COPY helloworld.go ./

RUN CGO_ENABLED=0 GOOS=linux go build -v -o helloworld

FROM alpine

COPY --from=builder /go/src/github.com/victorsalaun/tekton-tutorial/helloworld /helloworld

ENV PORT 8080

CMD ["/helloworld"]
