# Colorful Image Colorization

---

### Overview
This project introduces a deep learning-based automatic image colorization model. Our method leverages convolutional neural networks to predict realistic colors for grayscale images. Additionally, we offer real-time, user-guided image colorization with learned deep priors, as presented in our SIGGRAPH 2017 work.


---

## Updates
**[September 2020 Update]**
- This repository has been updated for minimal test-time usage with PyTorch.
- Added support for our SIGGRAPH 2017 model, which allows both automatic and interactive colorization.
- The original Caffe implementation is available in the [Caffe branch](https://github.com/richzhang/colorization/tree/caffe), but it is no longer maintained.

---

## Installation
To use this repository, clone it and install the necessary dependencies:

```bash
git clone https://github.com/richzhang/colorization.git
pip install -r requirements.txt
```

---

## Usage

### Colorizing an Image
To colorize an image using our pre-trained model, run:

```bash
python demo_release.py -i imgs/ansel_adams3.jpg
```

The output will be saved in the `imgs_out` folder.

---

### Loading Pre-trained Models in Python
Our models can be loaded and used programmatically as follows:

```python
import colorizers
colorizer_eccv16 = colorizers.eccv16().eval()
colorizer_siggraph17 = colorizers.siggraph17().eval()
```

For details on model usage, refer to [demo_release.py](demo_release.py). The processing pipeline includes:
- Conversion to Lab color space
- Resizing to 256x256
- Colorization
- Concatenation with the original full-resolution image
- Conversion back to RGB

---






---

## Contact
For questions or comments, please contact Richard Zhang at **rich.zhang [at] eecs.berkeley.edu**.

