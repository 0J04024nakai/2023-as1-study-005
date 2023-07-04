FROM alpine as builder
RUN apk add --no-cache gcc make musl-dev
COPY src /work
RUN cd /work; make

FROM alpine
COPY --from=builder /work/hello /usr/local/bin/hello
CMD ["hello"]
# FROM ubuntu:22.04 as builder
# COPY src /work
# RUN apt-get update; \
#     apt-get install -y gcc make; \
#     cd /work; make; \
#     apt-get purge --auto-remove --purge -y gcc make; \
#     rm -fr /var/lib/apt
# CMD ["/work/hello"]

# FROM ubuntu:22.04
# COPY --from=builder /work/hello /usr/local/bin/hello
# CMD ["hello"]



