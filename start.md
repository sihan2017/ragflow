# 后端源码启动
source .venv/bin/activate
export PYTHONPATH=$(pwd);
export HF_ENDPOINT=https://hf-mirror.com;
JEMALLOC_PATH=$(pkg-config --variable=libdir jemalloc)/libjemalloc.so;
LD_PRELOAD=$JEMALLOC_PATH python rag/svr/task_executor.py 1;

source .venv/bin/activate
export PYTHONPATH=$(pwd);
export HF_ENDPOINT=https://hf-mirror.com;
python api/ragflow_server.py;