From {{ JUPYTERLITE_BASE_DOCKER_IMAGE }}

RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \ 
    apt update && \
    apt install -y build-essential

RUN mkdir jupyterlite

COPY requirements.txt /jupyterlite
WORKDIR /jupyterlite
RUN pip install -r requirements.txt

{% if JUPYTERLITE_FULL_INSTALL %}
COPY requirements-full.txt /jupyterlite/
WORKDIR /jupyterlite
RUN pip install -r requirements-full.txt
{% endif %}

ENV JUPYTERLITE_PORT=8000
ENV JUPYTERLITE_OUTPUT_DIR=dist

ENTRYPOINT [ "jupyter", "lite", "serve"]

EXPOSE 8000