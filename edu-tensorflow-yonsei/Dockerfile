ARG BASE_IMAGE
FROM ${BASE_IMAGE}

ENV PIP_BREAK_SYSTEM_PACKAGES=1

RUN pip install --no-cache-dir --no-deps tensorflow-model-optimization && \
    pip install --no-cache-dir dm-tree mock scipy six && \
    pip install --no-cache-dir opencv-python-headless "numpy<2"

EXPOSE 8888
CMD ["sh", "-c", "exec jupyter lab --ip=0.0.0.0 --port=8888 --no-browser --allow-root --ServerApp.token=\"${JUPYTER_TOKEN:-}\" --ServerApp.root_dir=/workspace"]