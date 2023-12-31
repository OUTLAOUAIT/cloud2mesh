<img src='docs/images/lizard2.gif' align="right" width=325>
<br><br><br>

# Point2Mesh in PyTorch
### SIGGRAPH 2020 [[Paper]](https://arxiv.org/abs/2005.11084) [[Project Page]](https://ranahanocka.github.io/point2mesh/)<br>

Point2Mesh is a technique for reconstructing a surface mesh from an input point cloud.
This approach "learns" from a single object, by optimizing the weights of a CNN to deform some initial mesh to shrink-wrap the input point cloud.

## Original Author

Give credit to the original author: [Rana Hanocka](https://www.cs.tau.ac.il/~hanocka/) and [Gal Metzer](https://www.linkedin.com/in/gal-metzer-512803a1/).

  ```
@article{Hanocka2020p2m,
  title = {Point2Mesh: A Self-Prior for Deformable Meshes},
  author = {Hanocka, Rana and Metzer, Gal and Giryes, Raja and Cohen-Or, Daniel},
  year = {2020},
  issue_date = {July 2020}, 
  publisher = {Association for Computing Machinery}, 
  volume = {39}, 
  number = {4}, 
  issn = {0730-0301},
  url = {https://doi.org/10.1145/3386569.3392415},
  doi = {10.1145/3386569.3392415},
  journal = {ACM Trans. Graph.}, 
}
```

# Modifications

Some changes have been made to the original code to make it compatible with the latest versions and run on Google Colab.

- Upgraded dependencies to the latest versions.
- Modified code snippets to comply with the latest syntax and best practices.
- Added compatibility for Google Colab.

# Getting Started

### Installation
- Clone this repo:
```bash
git clone https://github.com/ranahanocka/cloud2mesh.git
cd cloud2mesh
```
#### Setup Conda Environment
- Relies on [PyTorch](https://pytorch.org/) version 2.1 and [PyTorch3D](https://github.com/facebookresearch/pytorch3d) version 0.7.5. <br>
Install via pip `requirements.txt` 

#### Install "Manifold" Software
This code relies on the [Robust Watertight Manifold Software](https://github.com/hjwdzh/Manifold). 
First ```cd``` into the location you wish to install the software. For example, we used ```cd ~/code```.
Then follow the installation instructions in the Watertight README.
```bash
%mkdir code
%cd code
!git clone https://github.com/hjwdzh/Manifold.git
%cd Manifold
%mkdir build
%cd build
!cmake .. -DCMAKE_BUILD_TYPE=Release
!make
```
If you installed Manifold in a different path than ```~/code/Manifold/build```, please update ```options.py``` accordingly (see [this line](https://github.com/ranahanocka/point2mesh/blob/767ac0ea0f5297b912eafd61a5cd2f60ec8c8490/options.py#L6))
  
# Running Examples
 
### Get Data
Download our example data
```bash
bash ./scripts/get_data.sh
```

### Running Reconstruction 
All the scripts can be found in ```./scripts/examples```.
Here are an example:

#### Noisy Guitar
```bash
bash ./scripts/examples/noisy_guitar.sh
```

# Running different Examples
You should provide an initial mesh file. If the shape has genus 0, you can use the convex hull script provided in ```./scripts/process_data/convex_hull.py```


# Questions / Issues
If you have questions or issues running this code, please open an issue.
