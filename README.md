# clip-interrogator

*Want to figure out what a good prompt might be to create new images like an existing one? The **CLIP Interrogator** is here to get you answers!*

## Run it!

Run Version 2 on Colab, HuggingFace, and Replicate!

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pharmapsychotic/clip-interrogator/blob/main/clip_interrogator.ipynb) [![Generic badge](https://img.shields.io/badge/🤗-Open%20in%20Spaces-blue.svg)](https://huggingface.co/spaces/pharma/CLIP-Interrogator) [![Replicate](https://replicate.com/cjwbw/clip-interrogator/badge)](https://replicate.com/cjwbw/clip-interrogator)


<br>

Version 1 still available in Colab for comparing different CLIP models 

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pharmapsychotic/clip-interrogator/blob/v1/clip_interrogator.ipynb) 


## About

The **CLIP Interrogator** is a prompt engineering tool that combines OpenAI's [CLIP](https://openai.com/blog/clip/) and Salesforce's [BLIP](https://blog.salesforceairesearch.com/blip-bootstrapping-language-image-pretraining/) to optimize text prompts to match a given image. Use the resulting prompts with text-to-image models like [Stable Diffusion](https://github.com/CompVis/stable-diffusion) on [DreamStudio](https://beta.dreamstudio.ai/) to create cool art!


## Using as a library

Create and activate a Python virtual environment
```bash
python3 -m venv ci_env
source ci_env/bin/activate
```

Install with PIP
```
pip install -e git+https://github.com/openai/CLIP.git@main#egg=clip
pip install -e git+https://github.com/pharmapsychotic/BLIP.git@lib#egg=blip
pip install clip-interrogator
```

You can then use it in your script
```python
from PIL import Image
from clip_interrogator import Interrogator, Config
image = Image.open(image_path).convert('RGB')
ci = Interrogator(Config(clip_model_name="ViT-L/14"))
print(ci.interrogate(image))
```
