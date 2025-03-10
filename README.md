# NeRF-Code-Analysis

이 저장소는 **NeRF(Neural Radiance Fields)** 의 핵심 개념을 소개하고, 실제로 구현한 Jupyter Notebook으로 구성되어있습니다.  
**카메라 행렬**, **계층적 샘플링과 볼륨 렌더링**, **NeRF의 네트워크 구조** 등, 핵심적인 개념을 순서대로 설명하고,
이것이 코드에서 어떻게 구현되었는지를 자세한 주석과 함께 소개합니다.

---

## 구조

```bash
.
├─ data
│   └─ nerf_synthetic
│       └─ lego          # 예시로 사용되는 synthetic 데이터 (lego 장면)
├─ frames                # 카메라의 이동 궤적에 대한 gif가 저장된 폴더
├─ 01 Camera Matrix.ipynb
├─ 02 Calculating Rays.ipynb
├─ 03 Volume Rendering.ipynb
├─ 04 NeRF Network.ipynb
├─ ...
└─ README.md
```

### `data/nerf_synthetic/lego`
- NeRF 논문에서 제공되는 예시 synthetic 장면 중 `lego` 데이터를 사용.
- 이미지, 카메라 파라미터 등 학습/검증에 필요한 자료가 들어 있습니다.

### `01 Camera Matrix.ipynb`
- **카메라 내부행렬(K)과 외부행렬([R|t])** 개념을 정리하고,  
- 픽셀 좌표가 월드 좌표로 투영되는 과정을 수식과 코드로 시각화하였습니다.

### `02 Calculating Rays.ipynb`
- **각 픽셀마다 광선(Ray)의 원점과 방향**을 구하는 과정을 다룹니다. 

### `03 NeRF Network.ipynb`
- **NeRF 신경망(MLP) 구조**를 구현하였습니다.
  - Positional Encoding  
  - Coarse/Fine 2개 네트워크 

### `04 Hierarchical Samling.ipynb`
- NeRF가 정교한 렌더링을 하기 위해 **계층적 샘플링(Volumetric Rendering)**을 수행하는 과정을 다룹니다.

### `05 Volume Rendering.ipynb`
- NeRF의 가장 중요한 개념 중 하나인 **볼륨 렌더링(Volumetric Rendering)**에 대한 설명입니다.

### `06 Blender Dataset Analysis.ipynb`
- NeRF의 대표적인 데이터셋인 **Blender Dataset**이 어떻게 구성되어있는지 살펴봅니다.

### `07 Blender Dataset Rendering.ipynb`
- Blender Dataset을 바탕으로 **광선의 생성부터 렌더링**까지의 파이프라인을 살펴봅니다.

### `08 Blender Dataset Training.ipynb`
- Blender Dataset을 바탕으로 **모델의 훈련 및 테스트**를 진행합니다.
  
파일은 앞으로 더 업데이트 될 예정입니다.

---
## 참고 문헌 및 강의

- **NeRF 논문**: *Mildenhall, Ben, et al.* "NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis." *ECCV 2020.
[https://github.com/bmild/nerf](https://github.com/bmild/nerf)


- **Fast Campus**: AI Paper : 논문 구현과 실습으로 배우는 NeRF
https://fastcampus.co.kr/data_online_nerfpaper

감사합니다! NeRF와 관련하여 궁금하신 점이나 수정할 내용이 있으면 이슈(issues)나 PR로 알려주세요.  
