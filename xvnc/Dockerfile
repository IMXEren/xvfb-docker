FROM debian:bookworm-slim

WORKDIR /usr/bin

RUN apt-get update -y && apt-get install --no-install-recommends -y \
  xvfb x11vnc \
  && rm -rf /var/lib/apt/lists/*

COPY entrypoint /entrypoint
RUN chmod +x /entrypoint

ENTRYPOINT ["/entrypoint"]
