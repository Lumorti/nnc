# NNC (Neural Net Compression)

### Description

A proof-of-concept image compression format utilising a neural network.

By removing data in a predefined patten, a file can be saved as a png with a lower file size than the original.
Since the removal locations are fixed, this image can be repeatedly compressed/decompressed in this manner without causing further data loss like with jpeg.
When the original image is required, a neural network is applied to draw in the missing pixels. 

Interestingly, the decompression can be done better on more powerful systems with a more well-trained network, independent of the compression hardware.
This also allows the format to scale with hardware. Graphics cards improving would theoretically eventually allow "lossless" compression with rates higher than with jpeg.
If images are required in their original quality they could be restored using a supercomputer, but if simply browsing the internet a simpler network could be used.

The current version here is still very much in development, it does function but can sometimes lead to artifacts due to the lack of network training.
So far a compression ratio of 2 works decently, 4 at a push, although it is rather image dependant. This will improve as I tweak the topology of the network and train it further.

All photos are licensed under the [Pixabay license](https://pixabay.com/service/license/) which allows noncommercial distribution.

### Example

TODO 

### Requirements

Requires python3, numpy, tensorflow and pillow:

```bash
sudo apt install python3 pip
pip3 install --upgrade tensorflow pillow numpy
```

To use your GPU for better performance, see the tensorflow installation guide.

### Usage

Use the following command in the cloned directory to view the command-line help:

```bash
./nnc --help
```

To compress an image use either:

```bash
./nnc --compress photo.jpg
./nnc -c photo.jpg
```

To decompress an image use either:

```bash
./nnc --decompress photo.nnc
./nnc -d photo.nnc
```

To retrain the neural network on some files (shouldn't be needed):

```bash
./nnc --train *.jpg 
./nnc -t *.jpg
```
