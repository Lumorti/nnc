# nnc

### Description

A proof-of-concept image compression format utilising a neural network.

By removing data in predefined places the resulting file is saved as a png with a lower file size than the original.
Since the line locations are fixed the image can be repeatedly compressed/decompressed without causing further data loss like with jpeg.
When the original image is required (for viewing or otherwise) a neural network is applied to draw in the missing pixels, effectively upscaling. 

All photos are licensed under the [Pixabay license](https://pixabay.com/service/license/) which allows noncommercial distribution.

### Efficiency

### Example


### Requirements

Requires python3, numpy, tensorflow and pillow:

```bash
sudo apt install python3 pip
pip3 install --upgrade tensorflow pillow numpy
```

To use your GPU for better performance, install tensorflow-gpu instead:

```bash
pip3 install tensorflow-gpu
```

### Usage

Use the following command in the cloned directory to view the command-line help:

```bash
./nnc --help
```

To compress an image:

```bash
./nnc --compress photo.jpg
```

To decompress an image:

```bash
./nnc --decompress photo.nnc
```

To retrain the neural network on some files (shouldn't be needed):

```bash
./nnc --train photo1.jpg photo2.jpg photo3.jpg photo4.jpg
```
