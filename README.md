# Beyond Periodicity: Towards a Unifying Framework for Activations in Coordinate-MLPs
This repository contains the code for "Beyond Periodicity: Towards a Unifying Framework for Activations in Coordinate-MLPs".

##Colab demo
An easy-to-get-started Colab demo for experimenting with novel activation functions proposed in the paper (coming soon)

##Training a NeRF
This code heavily relies on the awesome NeRF implementation provided [here](https://github.com/yenchenlin/nerf-pytorch).

## Installation

```
git clone https://github.com/yenchenlin/nerf-pytorch.git
cd nerf-pytorch
pip install -r requirements.txt
```

<details>
  <summary> Dependencies (click to expand) </summary>
  
  ## Dependencies
  - PyTorch 1.4
  - matplotlib
  - numpy
  - imageio
  - imageio-ffmpeg
  - configargparse
  
</details>

## Downloading data

Download data for two example datasets: `lego` and `fern`

```
bash download_example_data.sh
```

### More Datasets
To train the network on other datasets, download the data [here](https://drive.google.com/drive/folders/128yBriW1IG_3NJ5Rp7APSTZsJqdJdfc1). Place the downloaded dataset according to the following directory structure:
```
├── configs                                                                                                       
│   ├── ...                                                                                     
│                                                                                               
├── data                                                                                                                                                                                                       
│   ├── nerf_llff_data                                                                                                  
│   │   └── fern                                                                                                                             
│   │   └── flower  # downloaded llff dataset                                                                                  
│   │   └── horns   # downloaded llff dataset
|   |   └── ...
|   ├── nerf_synthetic
|   |   └── lego
|   |   └── ship    # downloaded synthetic dataset
|   |   └── ...
```

## Training

To train a Gaussian activated NeRF without positional encoding on the lego scene:
```
python run_nerf.py --config configs/lego.txt
```
After training for 500k iterations you can find the following video at `logs/lego_test/lego_test_spiral_500000_rgb.mp4`.

![](https://user-images.githubusercontent.com/7057863/78473103-9353b300-7770-11ea-98ed-6ba2d877b62c.gif)

---

To train NeRF on different datasets: 

```
python run_nerf.py --config configs/{DATASET}.txt
```

replace `{DATASET}` with `trex` | `horns` | `flower` | `fortress` | `lego` | etc.

---

To test NeRF trained on different datasets: 

```
python run_nerf.py --config configs/{DATASET}.txt --render_only
```

replace `{DATASET}` with `trex` | `horns` | `flower` | `fortress` | `lego` | etc.

  
[//]: # (<img src='imgs/pipeline.jpg'/>)


## Citation
If you find our work useful to your research, please cite
```
@inproceedings{ramasinghe2022beyond,
  title={Beyond periodicity: towards a unifying framework for activations in coordinate-MLPs},
  author={Ramasinghe, Sameera and Lucey, Simon},
  booktitle={Computer Vision--ECCV 2022: 17th European Conference, Tel Aviv, Israel, October 23--27, 2022, Proceedings, Part XXXIII},
  pages={142--158},
  year={2022},
  organization={Springer}
}

```

