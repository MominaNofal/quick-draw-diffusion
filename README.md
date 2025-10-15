# quick-draw-diffusion

This project processes a sample of 5 classes from the [Google Quickdraw Dataset](https://github.com/googlecreativelab/quickdraw-dataset) and trains a class-conditioned diffusion model on it using the Huggingface UNet2DModel. 

The dataset is processed initially in quick_draw_dataset.ipynb to pick the five classes: `banana, apple, broom, brocolli, birthday cake` and pick up 1000 samples from each.
Then the diffusion model is build in cond_diffuser.ipynb. The images are reshaped to 32x32 with white padding to make it easier to downscale and upscale in the UNet. The class labels encoded as integers are passed in as a seperate channel alongside the image data. The learning problem is modelled as prediction of the noise per timestep given the class label. The model is trained for 50 epochs using mse loss and adam optimizer.


A sample of the generation results:


<img width="512" height="64" alt="Unknown" src="https://github.com/user-attachments/assets/94d79a64-6357-478e-afd7-c516ee5a6375" />

see if you can guess the labels!
