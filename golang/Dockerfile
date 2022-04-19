# syntax=docker/dockerfile:1

FROM golang:1.17-alpine AS builder

ARG UID=999
ARG GID=999

WORKDIR /app

COPY go.mod ./
COPY go.sum ./

RUN go mod download

COPY *.go ./

RUN go build -o /app-api

EXPOSE 8080

ENTRYPOINT ["/app-api"]