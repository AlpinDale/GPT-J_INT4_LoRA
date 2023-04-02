# GPT-J Lora 4bit
Forked from [johnsmith0031/alpaca_lora_4bit](https://github.com/johnsmith0031/alpaca_lora_4bit)

Code for training a LoRA for the GPT-J model (and its variants) with 4-bit integer support. Should cut down the VRAM required by a considerable amount.

Still untested.

# Requirements
- gptq-for-llama <br>
- peft<br>

The specific version is inside `requirements.txt`<br>

# Install

```
pip install -r requirements.txt
```

# Finetune
After installation, this script can be used:

```
python finetune.py
```

# Inference

After installation, this script can be used:

```
python inference.py
```

# Text Generation Webui Monkey Patch

Clone the latest version of text generation webui and copy all the files into ./text-generation-webui/
```
git clone https://github.com/oobabooga/text-generation-webui.git
```

Open server.py and insert a line at the beginning
```
import custom_monkey_patch # apply monkey patch
import gc
import io
...
```

Use the command to run

```
python server.py
```
