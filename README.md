cd apptainer_image

apptainer build <SIF_FILE> <DEF_FILE>

cd ..

apptainer shell --nv --bind <PATH_TO_HOST_WORKDIR>:/workspace <PATH_TO_SIF_FILE>

cd <PATH_TO_HOST_WORKDIR>

uv venv .venv -p 3.11.12

source .venv/bin/activate

uv pip install -r requirements.txt

jupyter lab --ip=0.0.0.0 --port=8888 --KernelSpecManager.ensure_native_kernel=False --NotebookApp.token=<TOKEN>