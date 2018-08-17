FROM golang:1.10 as builder
COPY kubernetes.go main.go ./
RUN go get github.com/gorilla/mux
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o /main main.go kubernetes.go

FROM gcr.io/distroless/base
COPY --from=builder /main .
CMD ["./main"]
