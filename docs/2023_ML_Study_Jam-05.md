# Introduction to Image Generation

## Contexts

* [Course](#course)
* [TIL](#til)

## Course

* [x] VIDEO: Introduction to Image Generation
* [ ] QUIZ: Introduction to Image Generation: Quiz

## TIL

### Image Generation Model Families

* Variational Autoencoders -VAEs
* Generative Adversarial Networks - GANs
* Autoregressive Models
* Flow-based Models

### Diffusion Model

* Use Cases
  * Unconditioned generation
    * Human face synthesis
    * Super-resolution
  * Conditioned generation
    * Text-to-image
    * Image inpainting
    * Text-guided image-to-image

* What is it?
  * source: [arxiv | Deep Unsupervised Learning using Nonequilibrium Thermodynamics](https://arxiv.org/pdf/1503.03585.pdf)

* Denoising Diffusion Probabilistic Models (DDPM)
  * In each step, add gaussian noise to the image.
  * In each step, remove gaussian noise from.(needs to be trained)
  * DDPM Training
    * Denoising Model: U-Net + Attention
    * Loss: Pixel-wise MSE => Update parameters of the denoising model
  * source: [arxiv | Improving the Improved Training of Wasserstein GANs: A Consistency Term and Its Dual Effect](https://arxiv.org/pdf/1803.01541.pdf)

## Notes of the wrong answers

Q. What is the goal of diffusion models?
A. To learn the latent structure of a dataset by modeling the way in which data points diffuse through the latent space
