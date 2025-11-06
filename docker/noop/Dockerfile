# VERSION 0.1.0
# Based on https://github.com/JanNash/docker_noop

FROM alpine:latest AS builder
COPY noop/noop.c /
RUN apk add --no-cache gcc musl-dev && gcc -static -o /noop /noop.c

FROM scratch

COPY --from=builder /noop /noop
CMD ["/noop"]
