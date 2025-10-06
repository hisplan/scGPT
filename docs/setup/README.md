# Setup

(*) This was tested and verified on 2025-10-06. It might not work in the future if there are breaking changes in the dependencies.

## HGU HPC

### Installation

```bash
conda create -y -n scgpt python=3.10.18 pip
conda activate scgpt
# pip install torch==2.3.0 torchtext==0.18.0
pip install torch==2.3.0 torchtext==0.18.0 torchvision==0.18.0 torchaudio==2.3.0
pip install scgpt==0.2.4 "flash-attn<1.0.5" jupyterlab
```

(*) Torch and torch text version must be exactly as above. For more details, please refer to the official installation guide of PyTorch and TorchText:
https://github.com/pytorch/text?tab=readme-ov-file#installation

### Verification

Run the following command to check the installed version of scGPT:

```bash
pip show scgpt
```

```
Name: scgpt
Version: 0.2.4
Summary: Large-scale generative pretrain of single cell using transformer.
Home-page: https://github.com/bowang-lab/scGPT
Author: Haotian
Author-email: subercui@gmail.com
License: MIT
Location: /usr/local/lib/python3.12/dist-packages
Requires: cell-gears, datasets, leidenalg, numba, orbax, pandas, scanpy, scib, scikit-misc, scvi-tools, torch, torchtext, typing-extensions, umap-learn
Required-by:
```

Run the following commands in your terminal:

```bash
ipython
```

Then, in the IPython shell, run the following. You should not see any error messages if everything is set up correctly:

```bash
import scgpt as scg
```

You might see some warnings such as below, but you can safely ignore this warning messages:

Torchtext deprecation warning:

```
/home/jychun/miniconda3/envs/scgpt/lib/python3.10/site-packages/torchtext/vocab/__init__.py:4: UserWarning:
/!\ IMPORTANT WARNING ABOUT TORCHTEXT STATUS /!\
Torchtext is deprecated and the last released version will be 0.18 (this one). You can silence this warning by calling the following at the beginnign of your scripts: `import torchtext; torchtext.disable_torchtext_deprecation_warning()`
  warnings.warn(torchtext._TORCHTEXT_DEPRECATION_MSG)
```

flash-attn not installed warning:

```
/home/jychun/miniconda3/envs/scgpt-test3/lib/python3.10/site-packages/scgpt/model/model.py:77: UserWarning: flash-attn is not installed, using pytorch transformer instead. Set use_fast_transformer=False to avoid this warning. Installing flash-attn is highly recommended.
```

## Google Colab

### Installation

To set up the environment in Google Colab, run the following commands in a Colab notebook cell:

```
!pip uninstall -y -q torch torchtext torchvision torchaudio

!pip install -q torch==2.3.0 torchtext==0.18.0 torchvision==0.18.0 torchaudio==2.3.0

!pip install -q scgpt==0.2.4 fsspec==2025.3.0
```

### Verification

Run the following. You should not see any error messages if everything is set up correctly:

```bash
import scgpt as scg
```

You might see some warnings such as below, but you can safely ignore this warning messages for now:

```
/usr/local/lib/python3.12/dist-packages/scgpt/model/model.py:21: UserWarning: flash_attn is not installed
  warnings.warn("flash_attn is not installed")
/usr/local/lib/python3.12/dist-packages/scgpt/model/multiomic_model.py:19: UserWarning: flash_attn is not installed
  warnings.warn("flash_attn is not installed")
/usr/local/lib/python3.12/dist-packages/torchtext/vocab/__init__.py:4: UserWarning:
/!\ IMPORTANT WARNING ABOUT TORCHTEXT STATUS /!\
Torchtext is deprecated and the last released version will be 0.18 (this one). You can silence this warning by calling the following at the beginnign of your scripts: `import torchtext; torchtext.disable_torchtext_deprecation_warning()`
  warnings.warn(torchtext._TORCHTEXT_DEPRECATION_MSG)
/usr/local/lib/python3.12/dist-packages/torchtext/utils.py:4: UserWarning:
/!\ IMPORTANT WARNING ABOUT TORCHTEXT STATUS /!\
Torchtext is deprecated and the last released version will be 0.18 (this one). You can silence this warning by calling the following at the beginnign of your scripts: `import torchtext; torchtext.disable_torchtext_deprecation_warning()`
  warnings.warn(torchtext._TORCHTEXT_DEPRECATION_MSG)
```
