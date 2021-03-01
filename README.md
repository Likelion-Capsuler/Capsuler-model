# Capsuler

Capusler is a service that automatically captions images and videos, with additinal features such as Translation, Speech Synthesis(Text-to-Speech), and Keyword Extraction.
> This project was supervised under <a href="mailto:repositivator@gmail.com">Daeyeon Jo</a> and <a href="https://k-digital.likelion.net/">AI School @ Likelion</a>.
<p align="center"><img src="https://github.com/Likelion-Capsuler/Capsuler-model/blob/main/images/capsuler_logo.png" width="400px" height="400px"></p>

## Image Captioning
An Image Captioning model is one that automatically generates text descriptions for images. You can read more about it <a href="https://www.tensorflow.org/tutorials/text/image_captioning">here</a>.

## Models
We used Inception V3 for Image Extraction and LSTM for Caption generation. Both of their model structures can be imported directly from tensorflow.keras.

## Requirements
There are some required libraries and modules in order to run the code notebooks. We used the Google Colab environment, so please take in note that some of the codes may not work if you're running on an environment with differnt library versions.

```python
from tensorflow import keras
from pillow import Image
from gensim import models
import matplotlib.pyplot as plt
import numpy as np
import opencv
```

## Datasets
- Images & English Captions: <a href="https://cocodataset.org/#download">MS COCO</a>
- Korean Captions: <a href="https://aihub.or.kr/keti_data_board/visual_intelligence">AI Hub</a>

## Jupyter notebooks
### 01. Image Encoding
- Resize every training & validation image to the following dimensions: (299,299)
> This is necessary in order to fit and train the inception V3. 
- Transfer the images into a np.array form.

### 02. Image Captioning (Eng, Kor)
- This notebook preprocesses every English/Korean caption using language embedding.
- Delete all unnecessary special symbols in each caption.
- Add 'STARTSEQ' and 'ENDSEQ' at the beggining and end of each caption for sequencing later on.
- Use the following preconstructed vectors for each language:
    - Glove for English
    - Fasttext for Korean

### 03. Video Captioning
- Use OpenCV to capture frames from a given video file.
- Decide how many fps to capture by resizing the numbers of the following code:
```python
vidcap.get(1)%30==0
```

## Results

Image | Generated Caption
--- | ---
<img src="https://github.com/Likelion-Capsuler/Capsuler-model/blob/main/images/image1.png" width="300px"> | People are surrounding table with cake
<img src="https://github.com/Likelion-Capsuler/Capsuler-model/blob/main/images/image2.png" height="300px"> | Wine glass on table with wine glass
<img src="https://github.com/Likelion-Capsuler/Capsuler-model/blob/main/images/image3.png" width="300px"> | Woman is holding wii controller


## Contributors
<table>
    <tr>
        <td align="center" width="130px" height="160px">
            <a href="https://github.com/vodkamitlime"><img height="100px" width="100px" src="https://avatars.githubusercontent.com/u/75682050?s=460&u=0988d14e9abb4f0105746182fca76a3c1e61de53&v=4" /></a>
            <br />
            <a href="https://github.com/vodkamitlime">vodkamitlime</a>
        </td>
       <td align="center" width="130px" height="160px">
            <a href="https://github.com/peeinnkim"><img height="100px" width="100px" src="https://avatars.githubusercontent.com/u/56428536?s=460&u=165ad716887e73c690555e5266aee46a66d37c9f&v=4" /></a>
            <br />
            <a href="https://github.com/peeinnkim">peeinnkim</a>
        </td>
        <td align="center" width="130px" height="160px">
            <a href="https://github.com/vimonth"><img height="100px" width="100px" src="https://avatars.githubusercontent.com/u/78515383?s=460&u=77b51db455fb6ef4e3176d2cdbfb27899989c17f&v=4" /></a>
            <br />
            <a href="https://github.com/vimonth">vimonth</a>
        </td>
         <td align="center" width="130px" height="160px">
            <a href="https://github.com/pizzasoomin"><img height="100px" width="100px" src="https://avatars.githubusercontent.com/u/78468049?s=460&u=8fbc9e222938108765216d97ec46e0b0c734a0dc&v=4" /></a>
            <br />
            <a href="https://github.com/pizzasoomin">pizzasoomin</a>
        </td>
         <td align="center" width="130px" height="160px">
            <a href="https://github.com/sseraa"><img height="100px" width="100px" src="https://avatars.githubusercontent.com/u/47420434?s=460&u=1d322d43b4325583a2a01f22ed80a66a940cb5d7&v=4" /></a>
            <br />
            <a href="https://github.com/sseraa">sseraa</a>
        </td>
    </tr>
    <tr>
      <td align="center">
        <a>Haeun</a>
       </td>
      <td align="center">
        <a>Hyunsun</a>
      </td>
      <td align="center">
           <a>Jaejun</a>
        </td>
        <td align="center">
            <a>Soomin</a>
        </td>
        <td align="center">
            <a>Hyunsun</a>
        </td>
    </tr>
</table>
