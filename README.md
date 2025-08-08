# my_MJPEG

The objective of this project is to gain a better understanding of video encoding/decoding (codec). The goal is to reproduce MJPEG.

## What is MJPEG?

MJPEG stands for Motion JPEG.
It is a video composed of a sequence of independently compressed JPEG images.

Each frame of the video is compressed separately in JPEG format.
There are no interframes (no temporal compression as in MPEG, H.264, etc.).
The video is therefore a sequence of JPEG files, played back quickly in succession.

✅ Advantages:
Easy to implement
Good individual image quality
Less latency: ideal for real-time streaming (surveillance cameras, webcams)
Less visible degradation during jumps or bugs

❌ Disadvantages:
Larger file size than modern video codecs
Not optimized for long videos or slow motion
Only spatial compression (no temporal compression)

## Roadmap

Image RGB
   ↓
Convertie en YCbCr
   ↓
Sous-échantillonnage (Cb, Cr)
   ↓
Découpe en blocs 8x8
   ↓
DCT → Fréquences
   ↓
Quantification → Pertes
   ↓
Codage (zigzag + Huffman)
   ↓
Fichier JPEG compressé
