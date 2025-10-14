FROM alpine

RUN apk add curl jq \
  && latest_tag=$(curl -Ls https://api.github.com/repos/nextcloud/notify_push/releases/latest | jq -r '.tag_name') \
  && wget https://github.com/nextcloud/notify_push/releases/download/${latest_tag}/notify_push-`uname -m`-unknown-linux-musl -O /notify_push \
  && chmod +x /notify_push \
  && /notify_push --version

EXPOSE 7867

CMD ["/notify_push"]
