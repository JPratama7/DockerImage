FROM debian:bullseye-slim

RUN apt-get update && apt-get install --no-install-recommends -y gnupg ca-certificates curl patchelf \
    && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys F23C5A6CF475977595C89F51BA6932366A755776  \
    && echo 'deb https://ppa.launchpadcontent.net/deadsnakes/ppa/ubuntu focal main' >> /etc/apt/sources.list \
    && echo 'deb-src https://ppa.launchpadcontent.net/deadsnakes/ppa/ubuntu focal main'>> /etc/apt/sources.list \
    && apt -y update \
    && apt -y install --no-install-recommends python3.10-full python3.10-dev \
                      clang build-essential build-essential libfuse-dev upx  \
    && curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py && python3.10 get-pip.py\
    && python3.10 -m pip install nuitka ordered-set zstandard \
    && apt-get purge -y curl ca-certificates \
    && apt-get autoremove -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*


ENTRYPOINT ["python3.10"]