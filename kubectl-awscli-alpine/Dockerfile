FROM alpine:3.7

RUN apk -v --update add \
        ca-certificates \
        python \
        py-pip \
        groff \
        less \
        mailcap \
        && \
    pip install --upgrade awscli==1.16.312 s3cmd==2.1.0 python-magic && \
    apk -v --purge del py-pip && \
    rm /var/cache/apk/*

VOLUME /root/.aws
VOLUME /project
WORKDIR /project

RUN apk --no-cache add openssl \
    && wget -q -O kubectl https://storage.googleapis.com/kubernetes-release/release/v1.19.0/bin/linux/amd64/kubectl \
    && chmod +x kubectl \
    && mv kubectl /usr/local/bin

ENTRYPOINT ["/bin/sh","-c"]
CMD [""]
