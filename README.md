# GPT-J Lora 4bit
Made some adjust for the code in peft and gptq for llama, and make it possible for lora finetuning with a 4 bits base model. The same adjustment can be made for 2, 3 and 8 bits.

# Requirements
gptq-for-llama <br>
peft<br>
The specific version is inside requirements.txt<br>

# Install
~copy files from GPTQ-for-LLaMa into GPTQ-for-LLaMa path and re-compile cuda extension~<br>
~copy files from peft/tuners/lora.py to peft path, replace it~<br>

**NOTE:** Install scripts are no longer needed! requirements.txt now pulls from forks with the necessary patches.

```
pip install -r requirements.txt
```

# Finetune
~The same finetune script from https://github.com/tloen/alpaca-lora can be used.~<br>

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
