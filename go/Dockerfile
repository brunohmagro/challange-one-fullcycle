FROM golang:alpine AS build-go

WORKDIR /usr/src/app

COPY . .

RUN go build hello.go

RUN rm -rf ./hello.go


# NEXT BUILD

FROM scratch

WORKDIR /usr/src/app

COPY --from=build-go /usr/src/app .

CMD [ "./hello" ]
