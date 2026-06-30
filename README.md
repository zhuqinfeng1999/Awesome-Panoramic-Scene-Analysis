<div align="center">

# 🌍 Awesome Panoramic Scene Analysis [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

**A curated reading list for panoramic / omnidirectional (360&deg;) scene analysis,**  
**from distortion-aware engineering to sphere-native foundation modeling.**

![Papers](https://img.shields.io/badge/Papers-141-1f6feb?style=flat-square) ![Topics](https://img.shields.io/badge/Topics-8-8957e5?style=flat-square) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-2da44e?style=flat-square)](#contributing) [![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey?style=flat-square)](#license) [![Non-Commercial](https://img.shields.io/badge/Use-Non--Commercial-red?style=flat-square)](#license) [![Academic Only](https://img.shields.io/badge/Research-Academic%20Only-orange?style=flat-square)](#license) ![Maintained](https://img.shields.io/badge/Maintained-yes-2da44e?style=flat-square)

</div>

---

> [!IMPORTANT]
> **License notice: academic, non-commercial use only.** This dataset (the curated list, its selection, and arrangement) is released under [CC BY-NC 4.0](#license). Commercial use of any kind is prohibited. It is provided solely for academic and non-commercial research.

## About

This list is the companion repository to the survey **_Panoramic Scene Analysis: A Survey from Distortion-Aware Engineering to Sphere-Native Foundation Modeling_** by Qinfeng Zhu and Lei Fan (Xi'an Jiaotong-Liverpool University). A panoramic image is not just a wide field-of-view photo: its signal lives on the 2-sphere, so every planar projection introduces distortion that breaks the assumptions behind standard vision architectures.

The 141 papers below are organized along the survey's two orthogonal axes, architectural design (how operators interact with spherical geometry) and training paradigm (how knowledge transfers across domains), and follow a single trajectory of deepening geometric commitment: projection-based adaptation, distortion-aware engineering, sphere-native modeling, and geometry-aware tokenization for foundation models. Each paper is filed under the section where it first appears in the survey.

> Found something missing or misfiled? Contributions are welcome. See [Contributing](#contributing).

## Contents

- [📖 1. Introduction: Surveys & Problem Landscape](#s1) <sub>(22)</sub>
- [🌐 2. Imaging Geometry & Problem Formulation](#s2) <sub>(20)</sub>
- [🧩 3. Learning on the Sphere: A Modeling Taxonomy](#s3) <sub>(25)</sub>
  - [Projection-Based Adaptation](#s3-1) <sub>(5)</sub>
  - [Distortion-Aware Operators & Architectures](#s3-2) <sub>(5)</sub>
  - [Sphere-Native Modeling](#s3-3) <sub>(8)</sub>
  - [Foundation-Model Interface Adaptation](#s3-4) <sub>(4)</sub>
  - [Domain Adaptation & Transfer](#s3-5) <sub>(3)</sub>
- [🏙️ 4. Scene Understanding: From Closed-Set to Open-World](#s4) <sub>(30)</sub>
  - [Semantic & Panoptic Segmentation](#s4-1) <sub>(8)</sub>
  - [Depth Estimation](#s4-2) <sub>(5)</sub>
  - [Room Layout & Surface Normals](#s4-3) <sub>(7)</sub>
  - [Unified Scene Understanding](#s4-4) <sub>(2)</sub>
  - [Foundation-Model-Assisted Understanding](#s4-5) <sub>(4)</sub>
  - [Open-World Perception](#s4-6) <sub>(3)</sub>
  - [Holistic Evaluation](#s4-7) <sub>(1)</sub>
- [💬 5. Vision-Language Understanding & Spatial Reasoning](#s5) <sub>(18)</sub>
  - [Why Panoramas Matter for VLMs](#s5-1) <sub>(5)</sub>
  - [VQA, Captioning & Grounding](#s5-2) <sub>(6)</sub>
  - [Geometry-Aware Encoding & Spatial Reasoning](#s5-3) <sub>(7)</sub>
- [🎥 6. Dynamic Panoramic Perception](#s6) <sub>(18)</sub>
  - [Single-Object Tracking](#s6-1) <sub>(3)</sub>
  - [Multi-Object Tracking](#s6-2) <sub>(4)</sub>
  - [Video Object Segmentation](#s6-3) <sub>(2)</sub>
  - [Optical Flow, Saliency & Activity](#s6-4) <sub>(7)</sub>
  - [Foundation Models & Embodied Scenes](#s6-5) <sub>(2)</sub>
- [🗂️ 7. Datasets, Benchmarks & Evaluation Protocols](#s7) <sub>(5)</sub>
- [🔭 8. Open Problems & Future Directions](#s8) <sub>(3)</sub>
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)
- [How to Cite](#how-to-cite)
- [License](#license)

---

<a id="s1"></a>

## 📖 1. Introduction: Surveys & Problem Landscape

_Survey papers on panoramic / omnidirectional vision and the foundational works that frame the perspective-to-panorama gap._  
<sub>**22 papers**</sub>

- **Review on panoramic imaging and its applications in scene understanding** `IEEE TIM 2022` [[paper]](https://ieeexplore.ieee.org/iel7/19/4407674/09927463.pdf)
- **Panorama: The rise of omnidirectional vision in the embodied ai era** `arXiv 2025` [[paper]](https://arxiv.org/abs/2509.12989)
- **Deep learning for omnidirectional vision: A survey and new perspectives** `arXiv 2022` [[paper]](https://arxiv.org/abs/2205.10468)
- **One flight over the gap: A survey from perspective to panoramic vision** `arXiv 2025` [[paper]](https://arxiv.org/abs/2509.04444)
- **Spherenet: Learning spherical representations for detection and classification in omnidirectional images** `ECCV 2018` [[paper]](https://openaccess.thecvf.com/content_ECCV_2018/papers/Benjamin_Coors_SphereNet_Learning_Spherical_ECCV_2018_paper.pdf) [[code]](https://github.com/BlueHorn07/sphereConv-pytorch)
- **Transfer beyond the field of view: Dense panoramic semantic segmentation via unsupervised domain adaptation** `IEEE T-ITS 2021` [[paper]](https://ieeexplore.ieee.org/iel7/6979/9826234/09599375.pdf?casa_token=gj_Q1zZ2ZxUAAAAA:ZZnduyZ9RMtZ2EaBsHREatGoPKZKnbPdIyRp9QL7-SdOcSjQ6RcMMUkeFOQoIfMi-m-PInP4Pc4)
- **Tangent images for mitigating spherical distortion** `CVPR 2020` [[paper]](https://openaccess.thecvf.com/content_CVPR_2020/papers/Eder_Tangent_Images_for_Mitigating_Spherical_Distortion_CVPR_2020_paper.pdf)
- **Bifuse: Monocular 360 depth estimation via bi-projection fusion** `CVPR 2020` [[code]](https://github.com/Yeh-yu-hsuan/BiFuse) <!-- TODO: add paper link -->
- **Distortion-aware convolutional filters for dense prediction in panoramic images** `ECCV 2018` [[paper]](http://openaccess.thecvf.com/content_ECCV_2018/papers/Keisuke_Tateno_Distortion-Aware_Convolutional_Filters_ECCV_2018_paper.pdf) [[code]](https://github.com/tdsuper/Distortion-aware-CNNs)
- **Bending reality: Distortion-aware transformers for adapting to panoramic semantic segmentation** `CVPR 2022` [[paper]](http://openaccess.thecvf.com/content/CVPR2022/papers/Zhang_Bending_Reality_Distortion-Aware_Transformers_for_Adapting_to_Panoramic_Semantic_Segmentation_CVPR_2022_paper.pdf)
- **PanoFormer: panorama transformer for indoor 360 depth estimation** `ECCV 2022` [[paper]](https://arxiv.org/abs/2203.09283) [[code]](https://github.com/zhijieshen-bjtu/PanoFormer)
- **Spherical cnns** `arXiv 2018` [[paper]](https://arxiv.org/abs/1801.10130) [[code]](https://github.com/daniilidis-group/spherical-cnn)
- **Learning so (3) equivariant representations with spherical cnns** `ECCV 2018` [[paper]](https://arxiv.org/abs/1711.06721) [[code]](https://github.com/daniilidis-group/spherical-cnn)
- **Gauge equivariant convolutional networks and the icosahedral CNN** `ICML 2019` <!-- TODO: add paper link -->
- **DeepSphere: a graph-based spherical CNN** `arXiv 2020` [[paper]](https://arxiv.org/abs/2012.15000) [[code]](https://github.com/deepsphere/deepsphere-pytorch)
- **Dense360: Dense understanding from omnidirectional panoramas** `arXiv 2025` [[paper]](https://arxiv.org/abs/2506.14471)
- **Sgat4pass: Spherical geometry-aware transformer for panoramic semantic segmentation** `arXiv 2023` [[paper]](https://arxiv.org/abs/2306.03403)
- **Omnisam: Omnidirectional segment anything model for uda in panoramic semantic segmentation** `ICCV 2025` <!-- TODO: add paper link -->
- **SAP: Segment Any 4K Panorama** `arXiv 2026` [[paper]](https://arxiv.org/abs/2603.12759)
- **Densepass: Dense panoramic semantic segmentation via unsupervised domain adaptation with attention-augmented context exchange** `IEEE ITSC 2021` [[paper]](https://arxiv.org/abs/2108.06383)
- **360sfuda++: Towards source-free uda for panoramic segmentation by learning reliable category prototypes** `IEEE TPAMI 2024` [[paper]](https://arxiv.org/abs/2404.16501) [[code]](https://github.com/zhengxuJosh/360SFUDA)
- **Goodsam: Bridging domain and capacity gaps via segment anything model for distortion-aware panoramic semantic segmentation** `arXiv 2024` [[paper]](https://arxiv.org/abs/2403.16370)

<div align="right"><a href="#contents">&#8679; back to top</a></div>

---

<a id="s2"></a>

## 🌐 2. Imaging Geometry & Problem Formulation

_Camera models, projection spaces (ERP, cubemap, tangent, HEALPix, spherical harmonics), and the geometric reasons perspective priors do not transfer._  
<sub>**20 papers**</sub>

- **A unifying theory for central panoramic systems and practical implications** `ECCV 2000` <!-- TODO: add paper link -->
- **A generic camera model and calibration method for conventional, wide-angle, and fish-eye lenses** `IEEE TPAMI 2006` <!-- TODO: add paper link -->
- **An enhanced unified camera model** `IEEE RA-L 2015` <!-- TODO: add paper link -->
- **The double sphere camera model** `3DV 2018` [[paper]](https://arxiv.org/abs/1807.08957)
- **3d scene geometry estimation from 360 imagery: A survey** `ACM CSUR 2022` [[paper]](https://dl.acm.org/doi/pdf/10.1145/3519021)
- **Spherically-weighted horizontally dilated convolutions for omnidirectional image processing** `SIBGRAPI 2024` <!-- TODO: add paper link -->
- **Cube padding for weakly-supervised saliency prediction in 360 videos** `CVPR 2018` [[paper]](http://openaccess.thecvf.com/content_cvpr_2018/papers/Cheng_Cube_Padding_for_CVPR_2018_paper.pdf)
- **Snap angle prediction for 360 panoramas** `ECCV 2018` <!-- TODO: add paper link -->
- **HEALPix: A framework for high-resolution discretization and fast analysis of data distributed on the sphere** `ApJ 2005` <!-- TODO: add paper link -->
- **Osrt: Omnidirectional image super-resolution with distortion-aware transformer** `CVPR 2023` [[paper]](https://openaccess.thecvf.com/content/CVPR2023/papers/Yu_OSRT_Omnidirectional_Image_Super-Resolution_With_Distortion-Aware_Transformer_CVPR_2023_paper.pdf)
- **How much position information do convolutional neural networks encode?** `arXiv 2020` [[paper]](https://arxiv.org/abs/2001.08248)
- **Depth Anything in 360: Towards Scale Invariance in the Wild** `arXiv 2025` [[paper]](https://arxiv.org/abs/2512.22819)
- **360Anything: Geometry-Free Lifting of Images and Videos to 360** `arXiv 2026` [[paper]](https://arxiv.org/abs/2601.16192)
- **Rethinking semantic segmentation from a sequence-to-sequence perspective with transformers** `CVPR 2021` [[paper]](https://arxiv.org/abs/2012.15840) [[code]](https://github.com/fudan-zvg/SETR)
- **Panda: Towards panoramic depth anything with unlabeled panoramas and mobius spatial augmentation** `CVPR 2025` [[paper]](https://arxiv.org/abs/2406.13378)
- **MTPano: Multi-Task Panoramic Scene Understanding via Label-Free Integration of Dense Prediction Priors** `arXiv 2026` [[paper]](https://arxiv.org/abs/2602.05330)
- **Structured3d: A large photo-realistic dataset for structured 3d modeling** `ECCV 2020` [[paper]](https://arxiv.org/abs/1908.00222) [[code]](https://github.com/bertjiazheng/Structured3D)
- **On the generalization of equivariance and convolution in neural networks to the action of compact groups** `ICML 2018` <!-- TODO: add paper link -->
- **Sphereuformer: A u-shaped transformer for spherical 360 perception** `CVPR 2025` <!-- TODO: add paper link -->
- **SO3UFormer: Learning Intrinsic Spherical Features for Rotation-Robust Panoramic Segmentation** `arXiv 2026` [[paper]](https://arxiv.org/abs/2602.22867)

<div align="right"><a href="#contents">&#8679; back to top</a></div>

---

<a id="s3"></a>

## 🧩 3. Learning on the Sphere: A Modeling Taxonomy

_The core two-axis taxonomy: architectural design (how operators meet spherical geometry) crossed with training and transfer paradigms._  
<sub>**25 papers**</sub>

<a id="s3-1"></a>
### Projection-Based Adaptation

- **GLPanoDepth: Global-to-local panoramic depth estimation** `IEEE TIP 2024` [[paper]](https://arxiv.org/abs/2202.02796)
- **Omnifusion: 360 monocular depth estimation via geometry-aware fusion** `CVPR 2022` [[paper]](https://arxiv.org/abs/2202.01323) [[code]](https://github.com/yuyanli0831/OmniFusion)
- **360MonoDepth: High-Resolution 360 Monocular Depth Estimation** `CVPR 2022` [[paper]](https://arxiv.org/abs/2111.15669) [[code]](https://github.com/manurare/360monodepth)
- **Unifuse: Unidirectional fusion for 360 panorama depth estimation** `IEEE RA-L 2021` [[paper]](https://arxiv.org/abs/2102.03550) [[code]](https://github.com/alibaba/UniFuse-Unidirectional-Fusion)
- **Elite360m: Efficient 360 multi-task learning via bi-projection fusion and cross-task collaboration** `arXiv 2024` [[paper]](https://arxiv.org/abs/2408.09336)

<a id="s3-2"></a>
### Distortion-Aware Operators & Architectures

- **Learning spherical convolution for fast features from 360 imagery** `NeurIPS 2017` [[paper]](https://proceedings.neurips.cc/paper/2017/file/0c74b7f78409a4022a2c4c5a5ca3ee19-Paper.pdf) [[code]](https://github.com/sammy-su/Spherical-Convolution)
- **Kernel transformer networks for compact spherical convolution** `CVPR 2019` [[paper]](https://openaccess.thecvf.com/content_CVPR_2019/papers/Su_Kernel_Transformer_Networks_for_Compact_Spherical_Convolution_CVPR_2019_paper.pdf)
- **Behind every domain there is a shift: Adapting distortion-aware vision transformers for panoramic semantic segmentation** `IEEE TPAMI 2024` [[paper]](https://ieeexplore.ieee.org/iel8/34/4359286/10546335.pdf)
- **Egformer: Equirectangular geometry-biased transformer for 360 depth estimation** `ICCV 2023` [[paper]](https://arxiv.org/abs/2304.07803)
- **Look at the neighbor: Distortion-aware unsupervised domain adaptation for panoramic semantic segmentation** `ICCV 2023` [[paper]](http://openaccess.thecvf.com/content/ICCV2023/papers/Zheng_Look_at_the_Neighbor_Distortion-aware_Unsupervised_Domain_Adaptation_for_Panoramic_ICCV_2023_paper.pdf)

<a id="s3-3"></a>
### Sphere-Native Modeling

- **Spherephd: Applying cnns on a spherical polyhedron representation of 360 images** `CVPR 2019` [[code]](https://github.com/KAIST-vilab/SpherePHD_public) <!-- TODO: add paper link -->
- **Hush: Holistic panoramic 3d scene understanding using spherical harmonics** `CVPR 2025` <!-- TODO: add paper link -->
- **Scalable and equivariant spherical CNNs by discrete-continuous (DISCO) convolutions** `arXiv 2022` [[paper]](https://arxiv.org/abs/2209.13603)
- **Scaling spherical cnns** `arXiv 2023` [[paper]](https://arxiv.org/abs/2306.05420)
- **Spin-weighted spherical cnns** `NeurIPS 2020` [[paper]](https://arxiv.org/abs/2006.10731)
- **Orientation-aware semantic segmentation on icosahedron spheres** `ICCV 2019` [[paper]](https://openaccess.thecvf.com/content_ICCV_2019/papers/Zhang_Orientation-Aware_Semantic_Segmentation_on_Icosahedron_Spheres_ICCV_2019_paper.pdf)
- **Deepsphere: Efficient spherical convolutional neural network with healpix sampling for cosmological applications** `Astron. Comput. 2019` [[paper]](https://arxiv.org/abs/1810.12186)
- **Equivariance versus augmentation for spherical images** `ICML 2022` [[code]](https://github.com/JanEGerken/sem_seg_s2cnn) <!-- TODO: add paper link -->

<a id="s3-4"></a>
### Foundation-Model Interface Adaptation

- **Sgformer: Spherical geometry transformer for 360 depth estimation** `IEEE TCSVT 2025` [[paper]](https://arxiv.org/abs/2404.14979)
- **Goodsam++: Bridging domain and capacity gaps via segment anything model for panoramic semantic segmentation** `arXiv 2024` [[paper]](https://arxiv.org/abs/2408.09115)
- **360-degree full-view image segmentation by spherical convolution compatible with large-scale planar pre-trained models** `ACM MM 2025` <!-- TODO: add paper link -->
- **Rotary position embedding for vision transformer** `ECCV 2024` <!-- TODO: add paper link -->

<a id="s3-5"></a>
### Domain Adaptation & Transfer

- **The cityscapes dataset for semantic urban scene understanding** `CVPR 2016` <!-- TODO: add paper link -->
- **Both style and distortion matter: Dual-path unsupervised domain adaptation for panoramic semantic segmentation** `CVPR 2023` [[paper]](https://openaccess.thecvf.com/content/CVPR2023/papers/Zheng_Both_Style_and_Distortion_Matter_Dual-Path_Unsupervised_Domain_Adaptation_for_CVPR_2023_paper.pdf)
- **Multi-source domain adaptation for panoramic semantic segmentation** `Information Fusion 2025` [[paper]](https://arxiv.org/abs/2408.16469)

<div align="right"><a href="#contents">&#8679; back to top</a></div>

---

<a id="s4"></a>

## 🏙️ 4. Scene Understanding: From Closed-Set to Open-World

_Dense prediction on the sphere, from supervised closed-set tasks through unified multi-task and foundation-model-assisted understanding to open-world perception._  
<sub>**30 papers**</sub>

<a id="s4-1"></a>
### Semantic & Panoptic Segmentation

- **Can we pass beyond the field of view? panoramic annular semantic segmentation for real-world surrounding perception** `IEEE IV 2019` [[paper]](https://ieeexplore.ieee.org/iel7/8792328/8813768/08814042.pdf?casa_token=d49sGIdeGhgAAAAA:Y3YMgKKgJDG2YGJA-iX908KCsMFTzRHr5rOvpJtsDKw60Dmgzsa0Bn3oGRpH4C7A1nfvxRpB0ks)
- **Pass: Panoramic annular semantic segmentation** `IEEE T-ITS 2019` [[paper]](https://ieeexplore.ieee.org/iel7/6979/9211608/08835049.pdf?casa_token=A2QJkU5vPwwAAAAA:LyH3MJXGz15J_XGmn2KloMegzfglxTYsFWcJ8hoAh41MkJLM-SpvbMVd6oZW7T2gkiqHBuLK1aA)
- **Capturing omni-range context for omnidirectional segmentation** `CVPR 2021` [[paper]](http://openaccess.thecvf.com/content/CVPR2021/papers/Yang_Capturing_Omni-Range_Context_for_Omnidirectional_Segmentation_CVPR_2021_paper.pdf)
- **Deformable mamba for wide field of view segmentation** `arXiv 2024` [[paper]](https://arxiv.org/abs/2411.16481)
- **Mamba4PASS: Vision Mamba for PAnoramic Semantic Segmentation** `Displays 2025` <!-- TODO: add paper link -->
- **Mamba-CNN Collaborative Learning for Panoramic Semantic Segmentation via Online Knowledge Distillation** `ESWA 2025` <!-- TODO: add paper link -->
- **Panoramic panoptic segmentation: Insights into surrounding parsing for mobile agents via unsupervised contrastive learning** `IEEE T-ITS 2023` [[paper]](https://ieeexplore.ieee.org/iel7/6979/4358928/10012449.pdf?casa_token=dOQ4dABD6NgAAAAA:GCs0h-PHfp6xpydRcRVtmZK8G4a46quWBiLauqZVVc04-M3OLDl9tebu3CjPsl7wmQag5U98fQs)
- **Occlusion-aware seamless segmentation** `ECCV 2024` [[paper]](https://arxiv.org/abs/2407.02182) [[code]](https://github.com/yihong-97/OASS)

<a id="s4-2"></a>
### Depth Estimation

- **Hrdfuse: Monocular 360 depth estimation by collaboratively learning holistic-with-regional depth distributions** `CVPR 2023` [[paper]](https://arxiv.org/abs/2303.11616)
- **Elite360d: Towards efficient 360 depth estimation via semantic-and distance-aware bi-projection fusion** `CVPR 2024` [[paper]](https://arxiv.org/abs/2403.16376)
- **Depth anywhere: Enhancing 360 monocular depth estimation via perspective distillation and unlabeled data augmentation** `NeurIPS 2024` [[paper]](https://arxiv.org/abs/2406.12849)
- **DA2: Depth Anything in Any Direction** `arXiv 2025` [[paper]](https://arxiv.org/abs/2509.26618)
- **Depth Any Panoramas: A Foundation Model for Panoramic Depth Estimation** `arXiv 2025` [[paper]](https://arxiv.org/abs/2512.16913)

<a id="s4-3"></a>
### Room Layout & Surface Normals

- **Layoutnet: Reconstructing the 3d room layout from a single rgb image** `CVPR 2018` [[paper]](https://arxiv.org/abs/1803.08999) [[code]](https://github.com/zouchuhang/LayoutNet)
- **Horizonnet: Learning room layout with 1d representation and pano stretch data augmentation** `CVPR 2019` [[paper]](https://arxiv.org/abs/1901.03861) [[code]](https://github.com/sunset1995/HorizonNet)
- **Led2-net: Monocular 360 layout estimation via differentiable depth rendering** `CVPR 2021` [[paper]](https://arxiv.org/abs/2104.00568)
- **Lgt-net: Indoor panoramic room layout estimation with geometry-aware transformer network** `CVPR 2022` [[paper]](https://arxiv.org/abs/2203.01824)
- **Disentangling orthogonal planes for indoor panoramic room layout estimation with cross-scale distortion awareness** `CVPR 2023` [[paper]](https://arxiv.org/abs/2303.00971) [[code]](https://github.com/zhijieshen-bjtu/DOPNet)
- **AtlantaNet: inferring the 3D indoor layout from a single 360 image beyond the Manhattan world assumption** `ECCV 2020` [[paper]](https://arxiv.org/abs/1903.08094) [[code]](https://github.com/crs4/AtlantaNet)
- **PanoNormal: Monocular Indoor 360 Surface Normal Estimation** `arXiv 2024` [[paper]](https://arxiv.org/abs/2405.18745)

<a id="s4-4"></a>
### Unified Scene Understanding

- **Hohonet: 360 indoor holistic understanding with latent horizontal features** `CVPR 2021` [[paper]](https://arxiv.org/abs/2011.11498) [[code]](https://github.com/sunset1995/HoHoNet)
- **Panelnet: Understanding 360 indoor environment via panel representation** `CVPR 2023` [[paper]](https://arxiv.org/abs/2305.09078)

<a id="s4-5"></a>
### Foundation-Model-Assisted Understanding

- **PanoSAMic: Panoramic Image Segmentation from SAM Feature Encoding and Dual View Fusion** `arXiv 2026` [[paper]](https://arxiv.org/abs/2601.07447)
- **Depth anything v2** `NeurIPS 2024` [[paper]](https://arxiv.org/abs/2406.09414) [[code]](https://github.com/DepthAnything/Depth-Anything-V2)
- **Unik3d: Universal camera monocular 3d estimation** `CVPR 2025` [[paper]](https://arxiv.org/abs/2503.16591) [[code]](https://github.com/lpiccinelli-eth/UniK3D)
- **Depth any camera: Zero-shot metric depth estimation from any camera** `CVPR 2025` [[paper]](https://arxiv.org/abs/2501.02464)

<a id="s4-6"></a>
### Open-World Perception

- **Open panoramic segmentation** `ECCV 2024` [[paper]](https://arxiv.org/abs/2407.02685) [[code]](https://github.com/JunweiZheng93/OPS)
- **Panoramic out-of-distribution segmentation** `arXiv 2025` [[paper]](https://arxiv.org/abs/2505.03539)
- **JOPP-3D: Joint Open Vocabulary Semantic Segmentation on Point Clouds and Panoramas** `arXiv 2026` [[paper]](https://arxiv.org/abs/2603.06168)

<a id="s4-7"></a>
### Holistic Evaluation

- **Pano3d: A holistic benchmark and a solid baseline for 360 depth estimation** `CVPR 2021` [[paper]](https://arxiv.org/abs/2109.02749)

<div align="right"><a href="#contents">&#8679; back to top</a></div>

---

<a id="s5"></a>

## 💬 5. Vision-Language Understanding & Spatial Reasoning

_Where the output is language: why panoramas help VLMs, the VQA / captioning / grounding tasks, and geometry-aware encoding for spatial reasoning._  
<sub>**18 papers**</sub>

<a id="s5-1"></a>
### Why Panoramas Matter for VLMs

- **BEVFormer: Learning Birds-Eye-View Representation from Multi-Camera Images via Spatiotemporal Transformers** `arXiv 2022` [[paper]](https://arxiv.org/abs/2203.17270)
- **Deeppanocontext: Panoramic 3d scene understanding with holistic scene context graph and relation-based optimization** `ICCV 2021` [[paper]](https://arxiv.org/abs/2108.10743)
- **More than the Sum: Panorama-Language Models for Adverse Omni-Scenes** `arXiv 2026` [[paper]](https://arxiv.org/abs/2603.09573)
- **Vision-and-language navigation: Interpreting visually-grounded navigation instructions in real environments** `CVPR 2018` <!-- TODO: add paper link -->
- **PanoGrounder: Bridging 2D and 3D with Panoramic Scene Representations for VLM-based 3D Visual Grounding** `arXiv 2025` [[paper]](https://arxiv.org/abs/2512.20907)

<a id="s5-2"></a>
### VQA, Captioning & Grounding

- **Visual question answering on 360 images** `WACV 2020` <!-- TODO: add paper link -->
- **Pano-avqa: Grounded audio-visual question answering on 360 videos** `ICCV 2021` <!-- TODO: add paper link -->
- **Query-based image captioning from multi-context 360 degree images** `EMNLP Findings 2023` <!-- TODO: add paper link -->
- **360dvd: Controllable panorama video generation with 360-degree video diffusion model** `CVPR 2024` [[paper]](https://openaccess.thecvf.com/content/CVPR2024/papers/Wang_360DVD_Controllable_Panorama_Video_Generation_with_360-Degree_Video_Diffusion_Model_CVPR_2024_paper.pdf)
- **PanoAffordanceNet: Towards Holistic Affordance Grounding in 360 Indoor Environments** `arXiv 2026` [[paper]](https://arxiv.org/abs/2603.09760)
- **Towards omnidirectional reasoning with 360-r1: A dataset, benchmark, and grpo-based method** `arXiv 2025` [[paper]](https://arxiv.org/abs/2505.14197)

<a id="s5-3"></a>
### Geometry-Aware Encoding & Spatial Reasoning

- **360 Image Perception with MLLMs: A Comprehensive Benchmark and a Training-Free Method** `arXiv 2026` [[paper]](https://arxiv.org/abs/2603.16179)
- **ODI-Bench: Can MLLMs Understand Immersive Omnidirectional Environments?** `arXiv 2025` [[paper]](https://arxiv.org/abs/2510.11549)
- **Are multimodal large language models ready for omnidirectional spatial reasoning?** `arXiv 2025` [[paper]](https://arxiv.org/abs/2505.11907)
- **PanoEnv: Exploring 3D Spatial Intelligence in Panoramic Environments with Reinforcement Learning** `arXiv 2026` [[paper]](https://arxiv.org/abs/2602.21992)
- **Spatialvlm: Endowing vision-language models with spatial reasoning capabilities** `CVPR 2024` <!-- TODO: add paper link -->
- **Spatial-mllm: Boosting mllm capabilities in visual-based spatial intelligence** `NeurIPS 2026` <!-- TODO: add paper link -->
- **On the Generalization Capacities of MLLMs for Spatial Intelligence** `arXiv 2026` [[paper]](https://arxiv.org/abs/2603.06704)

<div align="right"><a href="#contents">&#8679; back to top</a></div>

---

<a id="s6"></a>

## 🎥 6. Dynamic Panoramic Perception

_Tracking, segmentation, and motion on panoramic video: distortion-varying motion, the wrap-around seam, persistent visibility, and ego-motion._  
<sub>**18 papers**</sub>

<a id="s6-1"></a>
### Single-Object Tracking

- **360vot: A new benchmark dataset for omnidirectional visual object tracking** `ICCV 2023` <!-- TODO: add paper link -->
- **360VOTS: Visual object tracking and segmentation in omnidirectional videos** `IEEE TPAMI 2025` <!-- TODO: add paper link -->
- **Robust and enhanced 360 visual tracking based on dynamic gnomonic projection** `J. R. Soc. NZ 2025` <!-- TODO: add paper link -->

<a id="s6-2"></a>
### Multi-Object Tracking

- **Omnidirectional multi-object tracking** `CVPR 2025` [[paper]](https://arxiv.org/abs/2503.04565) [[code]](https://github.com/xifen523/OmniTrack)
- **OmniTrack++: Omnidirectional Multi-Object Tracking by Learning Large-FoV Trajectory Feedback** `arXiv 2025` [[paper]](https://arxiv.org/abs/2511.00510)
- **Jrdb: A dataset and benchmark of egocentric robot visual perception of humans in built environments** `IEEE TPAMI 2021` <!-- TODO: add paper link -->
- **Jrdb-panotrack: An open-world panoptic segmentation and tracking robotic dataset in crowded human environments** `CVPR 2024` <!-- TODO: add paper link -->

<a id="s6-3"></a>
### Video Object Segmentation

- **Panovos: Bridging non-panoramic and panoramic views with transformer for video segmentation** `ECCV 2024` [[paper]](https://arxiv.org/abs/2309.12303) [[code]](https://github.com/shilinyan99/PanoVOS)
- **Leader360V: A Large-scale, Real-world 360 Video Dataset for Multi-task Learning in Diverse Environment** `NeurIPS 2026` [[paper]](https://arxiv.org/abs/2506.14271)

<a id="s6-4"></a>
### Optical Flow, Saliency & Activity

- **PanoFlow: Learning 360 optical flow for surrounding temporal understanding** `IEEE T-ITS 2023` <!-- TODO: add paper link -->
- **Saliency detection in 360 videos** `ECCV 2018` [[paper]](https://arxiv.org/abs/2209.08956)
- **Panoramic vision transformer for saliency detection in 360 videos** `ECCV 2022` [[paper]](https://arxiv.org/abs/2209.08956)
- **PAV-SOD: A new task towards panoramic audiovisual saliency detection** `ACM TOMM 2023` <!-- TODO: add paper link -->
- **Panoramic video salient object detection with ambisonic audio guidance** `AAAI 2023` [[paper]](https://arxiv.org/abs/2211.14419)
- **Panoramic human activity recognition** `ECCV 2022` <!-- TODO: add paper link -->
- **Adafpp: Adapt-focused bi-propagating prototype learning for panoramic activity recognition** `ACM MM 2024` <!-- TODO: add paper link -->

<a id="s6-5"></a>
### Foundation Models & Embodied Scenes

- **PanoSAM2: Lightweight Distortion-and Memory-aware Adaptions of SAM2 for 360 Video Object Segmentation** `arXiv 2026` [[paper]](https://arxiv.org/abs/2604.07901)
- **Habitat: A platform for embodied ai research** `ICCV 2019` [[code]](https://github.com/facebookresearch/habitat-lab) <!-- TODO: add paper link -->

<div align="right"><a href="#contents">&#8679; back to top</a></div>

---

<a id="s7"></a>

## 🗂️ 7. Datasets, Benchmarks & Evaluation Protocols

_The data infrastructure behind the field and the spherical-area / seam / polar metrics that current protocols still miss._  
<sub>**5 papers**</sub>

- **Joint 2d-3d-semantic data for indoor scene understanding** `arXiv 2017` [[paper]](https://arxiv.org/abs/1702.01105)
- **Matterport3d: Learning from rgb-d data in indoor environments** `arXiv 2017` [[paper]](https://arxiv.org/abs/1709.06158)
- **Omnidepth: Dense depth estimation for indoors spherical panoramas** `ECCV 2018` [[paper]](https://openaccess.thecvf.com/content_ECCV_2018/papers/NIKOLAOS_ZIOULIS_OmniDepth_Dense_Depth_ECCV_2018_paper.pdf) [[code]](https://github.com/meder411/OmniDepth-PyTorch)
- **Recognizing scene viewpoint using panoramic place representation** `CVPR 2012` [[paper]](https://dspace.mit.edu/bitstream/handle/1721.1/90932/Torralba_Recognizing%20scene.pdf?sequence=1)
- **Weighted-to-spherically-uniform quality evaluation for omnidirectional video** `IEEE SPL 2017` [[paper]](https://ieeexplore.ieee.org/iel7/97/7981445/07961186.pdf?casa_token=f8680-qtQdgAAAAA:S1OfbSK34TGdNC2qCowRtXJ_PiTvQ4qs-EyVePrbjRrb3M2wcBFAPXd_73cfZjF27lbRYsl5jNI)

<div align="right"><a href="#contents">&#8679; back to top</a></div>

---

<a id="s8"></a>

## 🔭 8. Open Problems & Future Directions

_Unified multimodal panoramic models and the open road toward general-purpose panoramic intelligence._  
<sub>**3 papers**</sub>

- **GPT-4o System Card** `Tech Report 2024` [[paper]](https://cdn.openai.com/gpt-4o-system-card.pdf)
- **Unified multimodal understanding and generation models: Advances, challenges, and opportunities** `arXiv 2025` [[paper]](https://arxiv.org/abs/2505.02567)
- **Scene parsing through ade20k dataset** `CVPR 2017` <!-- TODO: add paper link -->

<div align="right"><a href="#contents">&#8679; back to top</a></div>

---

<a id="contributing"></a>

## Contributing

Contributions are very welcome. To add a paper:

1. Open a pull request that adds the entry under the most relevant section.
2. Keep the existing format: `**Title** [[paper]](link)` followed by a `` `Venue Year` `` and the first author.
3. Prefer an official or arXiv link, and place the paper in the section where it best fits thematically.

Please keep one paper per line and preserve alphabetical or chronological ordering within a group where possible.

---

<a id="how-to-cite"></a>

## How to Cite

If this list or the survey is useful in your research, please consider citing:

```bibtex
@article{zhu2026panoramicsceneanalysissurvey,
      title={Panoramic Scene Analysis: A Survey from Distortion-Aware Engineering to Sphere-Native Foundation Modeling}, 
      author={Qinfeng Zhu and Lei Fan},
      journal={arXiv preprint arXiv:2606.27745},
      year={2026},
}
```

---

<a id="disclaimer"></a>

## Disclaimer

This repository is a curated reading list and research resource. It indexes and references academic papers, datasets, and benchmarks that are created and owned by third parties. All links point to external sources, and the papers, datasets, code, and other materials referenced in (and, where applicable, redistributed through) this repository remain subject to the licenses and terms set by their respective owners.

Many of the datasets and benchmarks referenced here are themselves released for academic or non-commercial research use only, and some carry further restrictions on redistribution, modification, or commercial exploitation. Because the underlying materials cannot be assumed to permit commercial use, and because aggregating restricted sources can create additional legal uncertainty, **no commercial use of this resource or its contents is permitted.**

The maintainers make no representation or warranty that any particular use of the referenced materials is lawful. Before using any referenced paper, dataset, or benchmark, you are solely responsible for reviewing and complying with the original license and terms of that source, and for obtaining any permissions required for your intended use. The maintainers accept no liability arising from any use of this resource or of the third-party materials it references. This resource is provided "as is", without warranty of any kind.

<div align="right"><a href="#contents">&#8679; back to top</a></div>

---

<a id="license"></a>

## License
[![CC BY-NC 4.0](https://licensebuttons.net/l/by-nc/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc/4.0/)

This work, meaning the curated list together with its selection, arrangement, and accompanying descriptions, is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/).

**This dataset is provided for academic and non-commercial research purposes only. Commercial use of any kind is strictly prohibited.** You are free to share and adapt the material for non-commercial purposes, as long as you give appropriate credit, provide a link to the license, and indicate if changes were made. For attribution, please cite the survey (see [How to Cite](#how-to-cite)).

The cited papers remain under their respective copyrights.
