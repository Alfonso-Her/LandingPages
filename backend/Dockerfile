FROM golang:1.25.5-alpine3.23

WORKDIR /app

COPY go.mod ./
# COPY go.sum ./ # Not created yet
RUN go mod download

COPY . .

CMD ["go", "run", "."]
