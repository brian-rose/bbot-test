# bbot-test

A simple repo with a Jupyter notebook just for testing some deployments via Binder and Binderbot

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/brian-rose/bbot-test/HEAD)


## Steps to execute the notebook via Binder from local command line using BinderBot

Run these steps from the root of this repo:

```
mamba create --name bbot python pip click aiohttp
conda activate bbot
python -m pip install git+https://github.com/pangeo-gallery/binderbot.git
python -m binderbot.cli --binder-url https://mybinder.org --repo brian-rose/bbot-test --ref main *.ipynb
```

This tells the BinderHub at https://mybinder.org to use an image based on the environment specified at https://github.com/brian-rose/bbot-test/blob/main/environment.yml, and within that environment, run whatever *.ipynb files are at the local path (which should be just the empty notebook `trivial-test.ipynb`).

After this finished running, the notebook should be rendered with its own output.
