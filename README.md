# NeRF 
This is a colab notebook implementation in pytorch of the NeRF paper in the form of tiny_nerf. The goal of this project is to represent a 3D scene in a compact way using a set of 2D images taken form different views and query this 3D scene to render new 2D views. The concept of a 3D scene is approached as a collection of discrete points where each harbors its own unique density attribute. While the density of these points remains constant, their coloration is dynamic and can change based on the angle from which they are observed. This variability in color is due to the assumption of non-Lambertian surfaces within the scene, which reflect light differently at varying angles of view, resulting in a rich and realistic rendering of 3D objects.

We represent a 3D scene using a 5D function that maps a 3D point in space (x, y, z) and a viewing direction (θ, φ) to the color emitted (r, g, b) and volume density (σ) at that point. This complex relationship is approximated by a multilayer perceptron (MLP) network, which maps these 5D inputs to their corresponding volume density and directionally emitted color. The MLP's weights are optimized during training to accurately predict color and density from any given 5D coordinate to render novel views of the scene.

![NeRF](https://github.com/Sahachar/NeRF/blob/main/NeRF_mapping.png)

The novel target and approximated views are below - 
![NeRF test view](https://github.com/Sahachar/NeRF/blob/main/Target_test.png)
![NeRF Results](https://github.com/Sahachar/NeRF/blob/main/Result_test.png)

Rendered 3D scene video with 180 frames in theta = (0,360) degrees
![NeRF_Result_Video](https://github.com/Sahachar/NeRF/blob/main/video.mp4)
