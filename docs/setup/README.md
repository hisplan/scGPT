# Setup

## HGU HPC

### Installation

```bash
conda create -y -n scgpt python=3.10.18 pip
conda activate scgpt
pip install torch==2.3.0 torchtext==0.18.0
pip install scgpt==0.2.4 "flash-attn<1.0.5" jupyterlab
```

### Verification

Run the following commands in your terminal:

```bash
ipython
```

Then, in the IPython shell, run the following. You should not see any error messages if everything is set up correctly:

```bash
import scgpt as scg
```

You might see some warnings such as below, but you can safely ignore this warning messages:

```
/home/jychun/miniconda3/envs/scgpt/lib/python3.10/site-packages/torchtext/vocab/__init__.py:4: UserWarning:
/!\ IMPORTANT WARNING ABOUT TORCHTEXT STATUS /!\
Torchtext is deprecated and the last released version will be 0.18 (this one). You can silence this warning by calling the following at the beginnign of your scripts: `import torchtext; torchtext.disable_torchtext_deprecation_warning()`
  warnings.warn(torchtext._TORCHTEXT_DEPRECATION_MSG)
```
