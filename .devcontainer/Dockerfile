ARG UV_VERSION=latest
ARG PYTHON_VERSION=3.13-slim

FROM ghcr.io/astral-sh/uv:${UV_VERSION} as uv
FROM python:${PYTHON_VERSION}

ENV PYTHONDONTWRITEBYTECODE=True \
    PYTHONUNBUFFERED=True \
    UV_LINK_MODE=copy


RUN apt-get update -qq \
    && apt-get install --no-install-recommends -y \
        build-essential \
        gcc \
        cmake \
        libcairo2-dev \
        libffi-dev \
        libpango1.0-dev \
        freeglut3-dev \
        ffmpeg \
        pkg-config \
        make \
        wget \
        ghostscript \
        fonts-noto \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*


ENV PATH=/usr/local/texlive/bin/armhf-linux:/usr/local/texlive/bin/aarch64-linux:/usr/local/texlive/bin/x86_64-linux:$PATH \
    TEXLIVE_INSTALL_URL=http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz

# Setup texlive with minimal installation
COPY .devcontainer/texlive-profile.txt /tmp/
RUN wget -O /tmp/install-tl-unx.tar.gz ${TEXLIVE_INSTALL_URL} \
    && mkdir /tmp/install-tl \
    && tar -xzf /tmp/install-tl-unx.tar.gz -C /tmp/install-tl --strip-components=1 \
    && /tmp/install-tl/install-tl --profile=/tmp/texlive-profile.txt \
    && tlmgr install \
        amsmath babel-english cbfonts-fd cm-super count1to ctex doublestroke dvisvgm everysel \
        fontspec frcursive fundus-calligra gnu-freefont jknapltx latex-bin \
        mathastext microtype multitoc physics prelim2e preview ragged2e relsize rsfs \
        setspace standalone tipa wasy wasysym xcolor xetex xkeyval \
    && rm -rf /tmp/*

ARG USER=manimuser
ARG USER_UID=1000

RUN adduser --disabled-password \
    --uid ${USER_UID} \
    ${USER}

COPY --from=uv --chown=${USER}: /uv /uvx /bin/
