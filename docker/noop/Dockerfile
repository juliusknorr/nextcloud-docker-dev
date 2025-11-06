# VERSION 0.1.0

FROM alpine:latest AS builder
COPY noop/noop.c /
RUN apk add --no-cache gcc musl-dev && gcc -static -o /noop /noop.c

FROM scratch
MAINTAINER Jan Nash <jnash@jnash.de>

COPY --from=builder /noop /noop
CMD ["/noop"]
