# StyleDubber
This package contains the accompanying code for the following paper:

"StyleDubber: Towards Multi-Scale Style Learning for Movie Dubbing", which has appeared as long paper in the Findings of the ACL, 2024.

![Illustration](./images/fig_intro_architecture.png)

## 📣 News




## 🗒 TODOs
- [x] Release StyleDubber's training and inference code.
- [x] Release pretrained weights.
- [x] Release the raw data and preprocessed data features of the GRID dataset.
- [x] Metrics Testing Scripts (SECS, WER_Whisper).
- [x] Release StyleDubber‘s Demo Pages at [here](https://acl2024x.github.io/StyleDubber/).
- [ ] Update README.md (How to use). 
- [ ] Release the preprocessed data features of the V2C-Animation dataset (chenqi-Denoise2).


## 📊 Dataset

- GRID ([BaiduDrive](https://pan.baidu.com/s/1E4cPbDvw_Zfk3_F8qoM7JA) (code: GRID) / GoogleDrive)
- V2C-Animation dataset (chenqi-Denoise2) 
  

## 💡 Checkpoints

We provide the pre-trained checkpoints on GRID and V2C-Animation datasets as follows, respectively:


- GRID: https://pan.baidu.com/s/1Mj3MN4TuAEc7baHYNqwbYQ (y8kb), [Google Drive](https://drive.google.com/file/d/1ehSKyKw_UkKiNJCcupujcLAmyTtvxaEY/view?usp=drive_link)

- V2C-Animation dataset (chenqi-Denoise2): https://pan.baidu.com/s/1hZBUszTaxCTNuHM82ljYWg (n8p5), [Google Drive](https://drive.google.com/file/d/1B3SIhActrdOEtVxktgW8K06_wf0GOeqN/view?usp=drive_link)

## ⚒️ Environment

Our python version is ```3.8.18``` and cuda version ```11.5```. It's possible to have other compatible version. 
Both training and inference are implemented with PyTorch on a
GeForce RTX 4090 GPU. 

```bash
conda create -n style_dubber python=3.8.18
conda activate style_dubber
pip install -r requirements.txt
```

## 🔥 Train Your Own Model 

You need repalce tha path in ```preprocess_config``` (see "./ModelConfig_V2C/model_config/MovieAnimation/config_all.txt") to you own path. 
Training V2C-Animation dataset (153 cartoon speakers), please run: 
```bash
python train_StyleDubber_V2C.py
```


You need repalce tha path in ```preprocess_config``` (see "./ModelConfig_GRID/model_config/GRID/config_all.txt") to you own path. 
Training GRID dataset (33 real-world speakers), please run:  
```bash
python train_StyleDubber_GRID.py
```

## ⭕ Inference 


![Illustration](./images/fig_Experiment.png)

```bash
python 0_evaluate_V2C_Setting1.py --restore_step 47000
```

```bash
python 0_evaluate_V2C_Setting2.py --restore_step 47000
```

```bash
python 0_evaluate_V2C_Setting3.py --restore_step 47000
```

## ✏️ Citing

If you find our work useful, please consider citing:
```BibTeX
@article{cong2024styledubber,
  title={StyleDubber: Towards Multi-Scale Style Learning for Movie Dubbing},
  author={Cong, Gaoxiang and Qi, Yuankai and Li, Liang and Beheshti, Amin and Zhang, Zhedong and Hengel, Anton van den and Yang, Ming-Hsuan and Yan, Chenggang and Huang, Qingming},
  journal={arXiv preprint arXiv:2402.12636},
  year={2024}
}
```

## 🙏 Acknowledgments

We would like to thank the authors of previous related projects for generously sharing their code and insights: [CDFSE_FastSpeech2](https://github.com/Labmem-Zhouyx/CDFSE_FastSpeech2), [Multimodal Transformer](https://github.com/yaohungt/Multimodal-Transformer), [SMA](https://github.com/keonlee9420/Stepwise_Monotonic_Multihead_Attention), [Meta-StyleSpeech](https://github.com/KevinMIN95/StyleSpeech), and [FastSpeech2](https://github.com/ming024/FastSpeech2).
