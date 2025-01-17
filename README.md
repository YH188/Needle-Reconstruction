# Needle-Reconstruction

Reconstruct the three-dimensional structure of an acupuncture needle handle from a single-view image.

1. **First, preprocess the input image** 
    - Perform background removal and resampling of the foreground object.
   <img src="front_rgba.png" alt="预处理后的图像" width="400"/>

2. **Use a two-stage framework to provide efficient 3D content generation for the Image-to-3D task.**
    - First, incorporate 3D Gaussian splatting into the generation task through SDS (Score Distillation Sampling) for efficient initialization.
    - Next, use block-wise local density queries and Color Back-projection to extract a textured mesh from the 3D Gaussians, employing an empirical threshold of 1 for Marching Cubes during mesh extraction.
    - Finally, in the UV-space refinement stage, use differentiable rendering to fine-tune the texture, yielding the final result.
    - <img src="generation.gif" alt="Generation Video" width="400"/>
    - [Download and watch the generation video](generation.mp4)
   
3. **Reconstruct the acupuncture needle handle.**

Note that you should [download and watch the reconstruction video](needleREconstruction.mp4) to see the reconstruction result.
