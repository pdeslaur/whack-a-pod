FROM golang:1.10 as builder
COPY main.go ./
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o /main main.go

FROM gcr.io/distroless/base
COPY --from=builder /main .
CMD ["./main"]

