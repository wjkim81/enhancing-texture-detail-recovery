# Enhancing Texture Detail Recovery in Low-Dose Fluoroscopic X-Ray Images with a Multi-Frame Deep Learning Framework

### Training the model
```
python train.py --model <model> --dataA <list of datasets>
```
### Test the mode
```
python test.py --model <model> [--test_datasets <list of data>]
```

### Genoray

| Algorithms   | PSNR (dB) | SSIM   |
|--------------|-----------|--------|
| Noise        | 39.955    | 0.938  |
| RED-CNN      | 49.506    | 0.994  |
| RDN          | 50.187    | 0.994  |
| WGAN-VGG     | 46.762    | 0.989  |
| U-Net (1)    | 47.178    | 0.992  |
| U-Net (2)    | 46.428    | 0.989  |
| U-Net (3)    | 49.348    | 0.993  |
| **Proposed** | 48.600    | 0.990  |

U-Net (1), U-Net (2), and U-Net (3) optimized the loss function specified in Eq. 1 and Eq. 4 and the summation of the
loss functions in Eq. 1 and Eq. 4 ($L_{1_{st}} + L_{2_{nd}}$)

For the various algorithms to compare the algorithms, check [wavelet-ldct-denoising](https://github.com/wjkim81/wavelet-ldct-denoising).

### Ablation Study
| Algorithms         | PSNR (dB) | SSIM  |
|--------------------|-----------|-------|
| Noise              | 39.955    | 0.938 |
| Single frame U-Net | 47.178    | 0.992 |
| Multi frame U-Net  | 51.391    | 0.994 |
| **Proposed**       | 48.600    | 0.990 |


### Choosing the number of frames

| # of frames | PSNR (dB) | SSIM  |
|-------------|-----------|-------|
| Noise       | 39.955    | 0.938 |
| 1           | 47.384    | 0.988 |
| 3           | 48.102    | 0.989 |
| 5           | 48.600    | 0.990 |
| 7           | 48.468    | 0.990 |