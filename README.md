# LLMs-on-personal-devices
### Towards building multimodal GPT-4 level chatbot

*llamafile* is the simple way to get started with **multimodal GPT-4 capabilities LLM** ((which means your input can be text and image) on your own computer. A llamafile is a single multi-GB file that contains both the model weights for an LLM and is bundled with a web UI for interacting with it. The baseline behind the llamafile is LLaVA 1.5 that is fine-tuned on top of Llama 2. 

# On Linux/Mac Platforms

Download the 4.26GB llamafile-server-0.1-llava-v1.5-7b-q4 file from repository on Hugging Face.

curl -LO https://huggingface.co/jartine/llava-v1.5-7B-GGUF/resolve/main/llava-v1.5-7b-q4-server.llamafile

Make that binary executable, by running this in a terminal:

chmod 755 llava-v1.5-7b-q4-server.llamafile

Run your new executable, which will start a web server on port 8080:

./llava-v1.5-7b-q4-server.llamafile

Navigate to http://127.0.0.1:8080/ to start interacting with the model in your browser.

# On Windows

# Trying out other models
The llamafile README currently links to binaries for Mistral-7B-Instruct, LLaVA 1.5 and WizardCoder-Python-13B.

You can also download a much smaller llamafile binary from their releases, which can then execute any model that has been compiled to GGUF format:

I grabbed llamafile-server-0.1 (4.45MB) like this:

curl -LO https://github.com/Mozilla-Ocho/llamafile/releases/download/0.1/llamafile-server-0.1
chmod 755 llamafile-server-0.1
Then ran it against a 13GB llama-2-13b.Q8_0.gguf file I had previously downloaded:

./llamafile-server-0.1 -m llama-2-13b.Q8_0.gguf
This gave me the same interface at http://127.0.0.1:8080/ (without the image upload) and let me talk with the model at 24 tokens per second.
