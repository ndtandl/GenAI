python3 -m venv .env
source .env/bin/activate

CMAKE_ARGS="-DLLAMA_METAL=on" FORCE_CMAKE=1 

pip3 install -r requirements.txt

git clone https://huggingface.co/TinyLlama/TinyLlama-1.1B-Chat-v1.0

python3 test.py

python3 chat.py --model_name_or_path ./models/Llama-2-7b-chat-hf

python3 chat.py --model_name_or_path ./models/Llama-2-7B-vietnamese-20k-GPTQ --is_4bit True

python3 chat.py --model_name_or_path ./models/TinyLlama-1.1B-Chat-v1.0

python3 chat.py --model_name_or_path ./models/CodeLlama-7b-hf

python3 chat.py --model_name_or_path codellama/CodeLlama-7b-Instruct-hf

python3 chat.py --model_name_or_path codellama/CodeLlama-7b-hf

python3 demo-chat-codellama.py --model_name_or_path codellama/CodeLlama-7b-Instruct-hf

python3 demo-chat-codellama.py --model_name_or_path /root/dev/genai/models/codeLlama-7b-text-to-sql

python3 llama2_for_langchain.py --model_name_or_path /mnt/f/TinyLlama/models/Llama-2-7b-chat-hf


python3 -c 'from huggingface_hub import hf_hub_download; downloaded_model_path = hf_hub_download(
                                                          repo_id="CompVis/stable-diffusion-v-1-4-original",
                                                          filename="sd-v1-4.ckpt",
                                                          use_auth_token=True
                                                         ); print(downloaded_model_path)'


bash <(curl -sSL https://g.bodaay.io/hfd) -m codellama/CodeLlama-7b-hf




export PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True


I add following env in the ~/.bashrc, then this issue fix.
export PATH=/usr/local/cuda/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH


git config --global user.name "ndtandl"
git config --global user.email "ndtandl@gmail.com"


Example:
"""
write code java spring boot example
"""