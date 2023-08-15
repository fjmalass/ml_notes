# Summary of Transformers


## Basic Models
1. GPT
2. OPT

## Quantization
* Ability to connect 4bits (3bits) []()

## Hacking Transformers

* [ChatGPT Hacking](https://llm-attacks.org/zou2023universal.pdf)
* [Github](https://github.com/llm-attacks/llm-attacks)

## Optimize prompts

* [PEZ](https://arxiv.org/pdf/2302.03668.pdf)

# HuggingFace and GPU with Rust

[YouTube](https://www.youtube.com/watch?v=p2qMNSd6mgk)
[GitHub](https://github.com/nogibjj/rust-pytorch-gpu-template/tree/main/translate)


# 3D Get Review

## Summary

* NVidia
* First to combine geometry and textures (including BRDF, base, metallic, roughness)
* Use Generative Adversarial Networks to train (GAN)


## Geometry Extraction

* **Geometry representation** using DMTet [Deep Marching Tetrahedra] (differentiable surface
representation that uses a signed distance field (SDF) on a tetrahedra gil. The surface is differentiably recovered.
[DMTet](https://nv-tlabs.github.io/DMTet/). [DeepNetTetrahedron Paper](https://arxiv.org/pdf/2111.04276.pdf)
* **Deformation** are computed via barycentric interpolation, i.e., each vertex is stored as a SDF `s`
and the initial canonical coordinate.
* **Neural Network** uses $R^{512}$ to `SDF` values and deformations at each vertex
* **Differentiable Mesh Extration** use *differentiable marching tetrahedra algorithm*

## Texture Generator

* **Texture representation** using a texture field
* Use `xatlas` [71]

## Training

* Training a separate model on each category, e.g., car, motorbike, chair
* From 300 to 7500 shapes per category
* From 24 to 100 random views for each shape (more views if fewer shapes)
* Training Set: ShapeNet and TurboSquid (as textures in ShapeNet are too simple), Body in RenderPeople (500 shapes)


## Comparison Metrics

* Geometry: *Chamfer Distance* (CD), *Light Field Distance*  (LFD) [10]
* Texture: *FID* [28]
* **MMD** Manifold to Manifold Distance
* **COV** Covariance


## Ablations (Influence of # parameters in models/inputs)

* Very sensitive to image resolution, used 128, 512, 1024 image resolutions, 1024 was best

## GANs to have tex-guided 3d Synthesis

* GAN using CLIP (Contrastive Language Image PreTraining) [CLIP](https://openai.com/research/clip)


## Comparison

* `Text2Mesh`


# Differentiable Renderer (DIB-R)

* [ArXiv](https://arxiv.org/abs/1908.01210)
* [GitHub](https://github.com/nv-tlabs/DIB-R-Single-Image-3D-Reconstruction)




