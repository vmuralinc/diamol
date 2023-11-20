#My optimized docker file
#FROM diamol/golang 
FROM diamol/golang AS builder 

WORKDIR web
COPY main.go .

RUN go build -o /web/server

#app
FROM diamol/base

CMD ["/web/server"]
WORKDIR web
COPY index.html .
COPY --from=builder /web/server .

ENV USER=sixeyed
EXPOSE 80

RUN chmod +x /web/server
