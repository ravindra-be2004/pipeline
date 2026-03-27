# Dockerfile for custom S2I CLI image
FROM registry.access.redhat.com/ubi8/ubi

ARG S2I_VERSION=1.5.0
#ARG S2I_URL=https://github.com/openshift/source-to-image/releases/download/v${S2I_VERSION}/source-to-image-v${S2I_VERSION}-linux-amd64.tar.gz
ARG S2I_URL=https://github.com/openshift/source-to-image/archive/refs/tags/v1.5.0.tar.gz
RUN dnf install -y curl tar && \
    curl -L $S2I_URL -o /tmp/s2i.tar.gz && \
    tar -xzf /tmp/s2i.tar.gz -C /tmp && \
    mv /tmp/s2i /usr/local/bin/s2i && \
    chmod +x /usr/local/bin/s2i && \
    s2i version

ENTRYPOINT ["s2i"]

