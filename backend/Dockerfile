FROM golang:1.22 as builder

WORKDIR /usr/src/app

# pre-copy/cache go.mod for pre-downloading dependencies and only redownloading them in subsequent builds if they change
COPY go.mod go.sum ./
RUN go mod download && go mod verify

COPY . .

RUN GOOS=linux go build -o /api ./cmd/api

CMD ['sh']


FROM gcr.io/distroless/base-debian12 AS build-release-stage

WORKDIR /
COPY --from=builder /api /api

EXPOSE 8081
CMD ["/api"]

# ENTRYPOINT ["/api"]

#FROM golang:1.22
#alpine:latest
#3.19.1
# WORKDIR /app
# COPY --from=builder /api /usr/local/bin/api
# EXPOSE 8081
# CMD ["/usr/local/bin/api"]