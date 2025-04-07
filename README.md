

# Deep Learning Based Data-Assisted Channel Estimation and Detection
This repository contains the code for the paper _Deep Learning Based Data-Assisted Channel Estimation and Detection_

## Framework

![image](./Fig/whole_frame.jpg)


## Requirements

Python 3.8 or later with all ```requirements.txt``` dependencies installed. To install run:
```bash
$ pip install -r requirements.txt
```

## Code
### Data Preparation
To generate channel.mat please use MATLAB. Check [here](https://www.etsi.org/deliver/etsi_tr/138900_138999/138900/14.02.00_60/tr_138900v140200p.pdf) for more details. 

### Command-line Arguments
| Argument         | Type     | Default        | Description                                                                 |
|------------------|----------|----------------|-----------------------------------------------------------------------------|
| `--datadir`      | `str`    | **(required)** | Path to the channel data.                                                   |
| `--hyp`          | `str`    | `"hyp/hyp.scratch.yaml"` | Path to the hyper parameters.                                                   |
| `--ues`          | `int`    | `2`            | Number of UEs                                                               |
| `--bss`          | `int`    | `4`            | Number of BSs                                                               |
| `--zdim`         | `int`    | `20`           | Latent variable dimension                                                   |
| `--datadir`      | `str`    | **(required)** | Path to the channel data.                                                   |
| `--cp`           | `int`    | `30`           | Cyclic prefix len.                            |
| `--subcarriers`  | `int`    | `256`          | Subcariers should be 128-256.                            |
| `--ltap`         | `int`    | `12`           | Number of TDL channel taps.                            |
| `--snrlist`      | `list`   | `[  -15, -10, -5, 0, 5,10]` | SNR list in experiments.                            |
| `--timesamplelist`| `list`  | `[  2, 4, 5,10]`| Pilot insertion intervals.                            |
| `--ofdmsymbols`  | `int`    | `21`           | Number of OFDM symbols (or time slots `T`).                                 |
| `--modscheme`    | `str`    | `QAM`          | Modulation scheme.                                  |
| `--repetition`   | `int`    | `1`            | Uses repetition coding if set `>1`                                          |
| `--num-epochs`   | `int`    | `50`           | Epochs                                          |
| `--esp`          | `int`    | `100`          | Early stop                                          |
| `--lr`           | `int`    | `1.0e-4`       | Learning rate                                          |
| `--save-dir  `   | `str`    | `""`             | Saving directory.                                     |
| `--name`         | `str`    | `'exp'`          | Add the name of current seed.       |
| `--project`      | `str`    | `'runs'`         | Add the name of project.       |




### Experiments
If you want run the experiments, you can directly run the ``main.py``. Each experiment config is commented in the `main` function as follow:
* CONVENTIONAL_CONFIG
* CONV_DATA_AIDED_CONFIG
* CHANNEL_TRACKING
* TORCH_DATA_AIDED
  
  - **Train example**:
```
python --datadir "/channel.mat" --hyp "hyp/hyp.scratch.yaml" --name "seed-0" --project "runs"
```
After running the code, results will be saved in `runs/seed-0` folder and the models are saved at the working directory.

### Results
To achieve results in the paper add convolutional coding scheme. Check [these](https://www.mathworks.com/help/comm/ref/convenc.html) examples. 

* BER-SNR and MSE-SNR for 16 and 64 QAM

<p align="center">
  <img src="./Figs/image1.gif" alt="Image 1" width="23%" style="margin: 1%;">
  <img src="./Figs/image2.gif" alt="Image 2" width="23%" style="margin: 1%;">
  <img src="./Figs/image3.gif" alt="Image 3" width="23%" style="margin: 1%;">
  <img src="./Figs/image4.gif" alt="Image 4" width="23%" style="margin: 1%;">
</p>

### Contribution
All contributions, bug reports, bug fixes, documentation improvements, enhancements, and ideas are welcome. However, be aware that socceraction is not actively developed. It's primary use is to enable reproducibility of our research. If you believe there is a feature missing, feel free to raise a feature request, but please do be aware that the overwhelming likelihood is that your feature request will not be accepted. To learn more on how to contribute, see the Contributor Guide.

### License
Distributed under the terms of the MIT license, socceraction is free and open source software. Although not strictly required, we appreciate it if you include a link to this repo or cite our research in your work if you make use of socceraction.

### Research and Cite
If you make use of this repository in your research or find it useful, please consider citing it: [to be updated]
