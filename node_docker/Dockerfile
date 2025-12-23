FROM golang:1.25.5-alpine3.23 AS go_builder
WORKDIR /app
COPY main.go ./
RUN go build -o app

FROM alpine:latest
WORKDIR /app
COPY --from=go_builder /app/app .
CMD [ "./app" ]