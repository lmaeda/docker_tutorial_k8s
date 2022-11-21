FROM golang:1.16 AS build

WORKDIR /compose/hello-docker
COPY main.go main.go
RUN CGO_ENABLED=0 go build -o hello main.go

FROM scratch
COPY --from=build /compose/hello-docker/hello /usr/local/bin/hello
CMD ["/usr/local/bin/hello"]
