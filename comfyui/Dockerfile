FROM ubuntu

RUN apt-get update
RUN apt-get install -y --no-install-recommends \
        git \
        python3 \
        python3-pip \
        python3-venv

RUN python3 -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

RUN pip install torch torchvision

RUN git clone https://github.com/comfyanonymous/ComfyUI.git /opt/comfyui
RUN pip install -r /opt/comfyui/requirements.txt

RUN git clone https://github.com/Comfy-Org/ComfyUI-Manager.git /opt/comfyui/custom_nodes/comfyui-manager
RUN pip install -r /opt/comfyui/custom_nodes/comfyui-manager/requirements.txt

EXPOSE 8188
WORKDIR /opt/comfyui
ENTRYPOINT ["python3", "main.py", "--listen"]