# Breaking-Captcha-Using-Machine-Learning

This project aims to see how robust a Captcha is, whether a machine learning algorithm is able to break the Captcha by correctly reading the text present in it. This is for educational purposes only and should not be used for nefarious tasks.

I have used Convolutional Neural Networks for this task.

### How to run the code:

Run extract_single_letters_from_captchas.py to split the Captcha's into single character images. Now we can just train the model for the task of Optical Character Recognition (OCR).

Run train_model.py to train the model. (I am not providing my trained model for security reasons).

Run solve_captchas_with_model.py to use your trained model to break Captcha's. Have fun!
