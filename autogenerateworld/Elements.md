## Elements
- 3D model generation
    - [POCO](https://github.com/valeoai/POCO)
    - [Dane-field App](https://github.com/Kitware/Danesfield-App)
    - [GET3D](https://github.com/nv-tlabs/GET3D)
- Character generation(Text to 3D)
    - [AvaratClip](https://hongfz16.github.io/projects/AvatarCLIP.html)
        - Advanced [EVA3D](https://hongfz16.github.io/projects/EVA3D.html)
    - [MotionDiffusion](https://mingyuan-zhang.github.io/projects/MotionDiffuse.html)
    - [DreamFusion](https://github.com/ashawkey/stable-dreamfusion)
    - [ICON](https://github.com/YuliangXiu/ICON)
        - cannot reconstruct anime character/cannot divide into species
- Auto Rigging
    - [RigNet](https://zhan-xu.github.io/rig-net/)
- 3d semantic segmentation/classification
    - [RandLANet](https://github.com/aRI0U/RandLA-Net-pytorch)
    - [BEVMap with Large Scenes](https://github.com/zouzhenhong98/SensatUrban-BEV-Seg3D)
    - [OpenMMLAB](https://mmdetection3d.readthedocs.io/en/latest/getting_started.html)
- Anime Image generation
    - [Waifu Diffusion](https://huggingface.co/hakurei/waifu-diffusion)
        - 数十枚の映像だけで追加学習が可能(https://note.com/lisa_s/n/n5fb5468e8998)


## requirements
- 16GB/32GB Memory GPU on AWS Cloud...

## Pipelines
(0-1)text input/input image -> avatar creation -> auto rigging
(0-2)GPS data/video data -> get 3d point clouds -> reconstruct high quality meshes
(1) import and auto-place/define walkable fields
(2) reflect the real data(human position/car position) -> object/semantic segmentation -> create car/person objects and adjust lighting

