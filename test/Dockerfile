FROM registry.alauda.cn:60080/devops/builder-go-121:latest

# Install kubectl
ARG KUBECTL_VERSION=v1.29.3
RUN rm -f $(which kubectl) && \
    wget https://storage.googleapis.com/kubernetes-release/release/${KUBECTL_VERSION}/bin/linux/amd64/kubectl -O /usr/local/bin/kubectl && \
    chmod +x /usr/local/bin/kubectl

# Install ko
ARG KO_VERSION=0.15.2
RUN curl -L https://github.com/google/ko/releases/download/v${KO_VERSION}/ko_${KO_VERSION}_Linux_x86_64.tar.gz > ko_${KO_VERSION}.tar.gz
RUN tar -C /usr/local/bin -xzf ko_${KO_VERSION}.tar.gz

# Install yq
ARG YQ_VERSION=4.42.1
RUN wget https://github.com/mikefarah/yq/releases/download/v${YQ_VERSION}/yq_linux_amd64 -O /usr/local/bin/yq && \
    chmod +x /usr/local/bin/yq

# Install python
RUN apt update && apt install -y --no-install-recommends \
    ca-certificates \
    python3 \
    python3-dev \
    python3-openssl \
    python3-pip \
    python3-setuptools \
    python3-wheel \
    jq \
    && rm -rf /var/lib/apt/lists/* \
    && update-alternatives --install /usr/bin/python python /usr/bin/python3 1 \
    && update-alternatives --install /usr/bin/pip pip /usr/bin/pip3 1
