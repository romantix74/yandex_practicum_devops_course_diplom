FROM golang:1.22 as builder

WORKDIR /usr/src/app

# pre-copy/cache go.mod for pre-downloading dependencies and only redownloading them in subsequent builds if they change
COPY go.mod go.sum ./
RUN go mod download && go mod verify

COPY . .

WORKDIR /usr/src/app/cmd/api
RUN go build -o /api

# RUN go run ./cmd/api

# # CMD ["go", "build"]
# CMD ["bash"]



FROM alpine:3
COPY --from=builder api /bin/api
ENTRYPOINT ["/bin/api"]