**NeRF for Lunar imagery**:

A neural radiance field (NeRF) is a neural network that can reconstruct complex 3D scenes from a partial set of 2D images. We capture images of a scene from different viewpoints so that these input 2D images to the NeRF model so that it analyses some features for each images such as:

    1) Intensity of light falling at that point
    2) The color of the light at a point
    3) Camera positioning
    4) Spatial information

Working of NeRF for 3D image rendering:

    1) Ray Generation:

    For each pixel in the desired output (the new view we want to render), NeRF generates a ray that originates from the 
    virtual camera's position and passes through that pixel. This ray represents the path of light that would reach that
    pixel in the rendered image.

    2) Sampling Along the Ray:

    Along each ray, NeRF takes multiple sample points. These samples represent points in the 3D space that the ray passes
    through. It is determining what color and density exists at various points along the path of the light ray

    3) Neural Network Evaluation:

    For each sample point, NeRF feeds its 3D coordinates and viewing direction into the neural network.   
    The neural network then outputs:
    The color of the light at that point (RGB values).   
    The volumetric density (how opaque the material is at that point).

    4) Volume Rendering:

    NeRF uses a technique called volume rendering to combine the color and density information from all the sample points 
    along the ray.
    
    This process simulates how light accumulates as it travels through the 3D scene.
    This is conceptually similar to simulating how light passes through a participating medium, like smoke or fog.
    Essentially, it integrates the color and opacity along the ray, with the opacity determining how much the color
    at a certain point contributes to the final pixel color. 
    The accumulated color and opacity along the ray will determine the color of the pixel in the new rendered image.


**Our Project Implementation of 3D reconstruction of 22D lunar images**:

1) We have converted all images to jpeg and resized them to 256,256 for easier and smooth operations on them for our deep learning model.
2) Since a fixed dataset for authentic lunar images by ISRO was unavailable on public platforms , i have taken them manually.
3) We have taken 90 images total since this was a basic project to understand and see working of NeRF models. For much more realistic and advanced projects we would need much more images as well as high computing units for effecient training.
4) The NeRF model generates depth maps.

what exactly is a depth map?

---> A depth map is essentially an image where each pixel's value represents the distance of a point in a scene from the viewpoint of a camera. These distances are represented as grayscale values.

---> They are crucial especially in AR VR environments.



This project is a very basic implementation of Neural radiance field models and might not be accurate. For actual implementations we would need proper dataset, advanced algorithms to estimate camera positions and coordinates since for these images no camera angle and information was attached.
Moreover, high end GPU's are important for training such large models.






   
