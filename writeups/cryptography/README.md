
pixelated

![scrambled1](https://github.com/user-attachments/assets/3899c4ae-60c6-4708-98c2-8fb0fbbd0d41)
![scrambled2](https://github.com/user-attachments/assets/f2529e7a-46e3-41b3-929c-3279e41e7cd5)
you run this code which contains the two images from the website 
you need to combine the two images in order to get the flag 
once you get the image generated you need to edit the pictures lightening in order to see the flag 
clearly 




# Install dependencies (only needed once)
!pip install pillow numpy

from PIL import Image
import numpy as np
from google.colab import files

# Upload images
uploaded = files.upload()

# Make sure the files are named correctly
im1 = Image.open("scrambled1.png")
im2 = Image.open("scrambled2.png")

# Convert images to numpy arrays
im1np = np.array(im1)
im2np = np.array(im2)

# XOR the two images
result = np.bitwise_xor(im1np, im2np).astype(np.uint8)

# Save the result
Image.fromarray(result).save("flag.png")

# Download the result
files.download("flag.png")
