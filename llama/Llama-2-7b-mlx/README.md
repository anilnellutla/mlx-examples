---
pipeline_tag: text-generation
inference: false
tags:
- facebook
- meta
- llama
- llama-2
- mlx
---

# **Llama 2**

Llama 2 is a collection of pretrained and fine-tuned generative text models ranging in scale from 7 billion to 70 billion parameters. This is the repository for the 7B fine-tuned model, in `npz` format suitable for use in Apple's MLX framework.

Weights have been converted to `float16` from the original `bfloat16` type, because `numpy` is not compatible with `bfloat16` out of the box.

```bash
# Install mlx, mlx-examples, huggingface-cli
pip install mlx
pip install huggingface_hub hf_transfer
git clone https://github.com/ml-explore/mlx-examples.git

# Download model
export HF_HUB_ENABLE_HF_TRANSFER=1
huggingface-cli download --local-dir Llama-2-7b-mlx mlx-llama/Llama-2-7b-mlx

# Run example
python mlx-examples/llama/llama.py Llama-2-7b-mlx/llama-2-7b.npz Llama-2-7b-mlx/tokenizer.model "My name is "
```

Please, refer to the [original model card](https://huggingface.co/meta-llama/Llama-2-7b/tree/main) for details on Llama 2.


