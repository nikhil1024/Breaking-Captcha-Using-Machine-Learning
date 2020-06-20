# Breaking-Captcha-Using-Machine-Learning

This project aims to see how robust a Captcha is, whether a machine learning algorithm is able to break the Captcha by correctly reading the text present in it. This is for educational purposes only and should not be used for nefarious tasks.

I have used Convolutional Neural Networks for this task.

The project was split up into 3 stages:
- Splitting captcha into individual letters and numbers.
- Training Neural Network
- Testing the trained model on breaking different captcha examples


### Splitting captcha:

Every captcha example was basically an image of 4 handwritten letters or numbers. They were first binarized (inversely) using cv2.THRESH_BINARY_INV | cv2.THRESH_OTSU 

Then the contours (connected regions of text) were found out using cv2.findContours(). Using this, the connected regions were separated. But, there’s a possibility that 2 or more letters (or numbers) were touching each other and they would be considered as one single region. But this would be incorrect. In order to counter this, a limiting condition was applied. Say, if the width of the connected region is 1.25 times its height, then it means that the connected region actually contains 2 or more letters or numbers attached to each other. In such a case, the connected region was cut in half and taken as 2 different regions. At the end of this step, we have all the letters and numbers separated.


### Training Neural Network:

These extracted letters and numbers were then used to train the neural network. The code was written in Python. A deep learning library called “Keras” was used for building the neural network. It was trained on NVIDIA GeForce GTX 1060 with MAXQ. It was trained for 10 epochs. The training and testing sets were split 75% : 25%. A near 100% accuracy was achieved.

### Testing the network:

Now we can test our network using our trained model. A sample output is shown below:

![predicted output sample] (https://github.com/nikhil1024/Breaking-Captcha-Using-Machine-Learning/blob/master/predicted_output_example.PNG)

### Libraries Required:

- Numpy
- OpenCV
- Sklearn
- Keras

### How to run the code:

Run extract_single_letters_from_captchas.py to split the Captcha's into single character images. Now we can just train the model for the task of Optical Character Recognition (OCR).

Run train_model.py to train the model. (I am not providing my trained model for security reasons).

Run solve_captchas_with_model.py to use your trained model to break Captcha's. Have fun!
