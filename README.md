
# WASD: Wireless Anomaly Signal Dataset

## Overview

WASD (Wireless Anomaly Signal Dataset) is designed for anomaly signal detection in wireless signals within fixed urban scenarios. It combines real-world signals measured across 19 LTE and 5G bands with simulated anomalous signals. This dataset is suitable for training various object detection networks and developing robust deep learning models for accurate and efficient anomaly detection in real-world environments.

## Paper Link
DOI:10.1109/ACCESS.2024.3521946 (https://ieeexplore.ieee.org/document/10813361)

## Related Works 
* Jinha Kim, Sunji Oh, Hyeongwoo Kim, and Byungkwan Kim, "Spectrum Anomaly Detection Using Deep Neural Networks: A Wireless Signal Perspective", IEEE Access, https://doi.org/10.1109/ACCESS.2025.3603216
  
*Hyeongwoo Kim, Jinha Kim, Youngseo Ji and Byungkwan Kim, "Anomaly Detection for Wireless Cellular Communication based on Synthetic Anomaly", IEEE Access, https://doi.org/10.1109/ACCESS.2025.3584113 

## Dataset Features

* **Real-world Measurement Data**: Includes real-world signal data collected from 19 LTE and 5G bands.
![image](./images/band_example.png)

* **Diverse Anomaly Signals**: Contains various types of simulated anomaly signals, including tone, chirp, and pulse signals.
* **Realistic Simulation**: Employs realistically feasible random-based parameters and configured fading channels in accordance with 3GPP standards to simulate real-world conditions.
![image](./images/fading_data_example.png)
![image](./images/data_synthesis.png)

* **Large-scale Dataset**: A comprehensive dataset comprising 85,500 samples across 19 bands.
* **Versatile Usage**: Includes both object detection and normal data, suitable for both supervised and unsupervised learning approaches.


## Notes on the ADC for power calibration (described in metadata json file)
* The iq_level_offset is a calibration correction expressed in dB, i.e., an offset applied to the raw IQ values (integer outputs from the ADC) to convert them into actual power levels in dBm.
* The reference_level specifies the absolute power level (in dBm) to which the raw IQ values correspond. The unit of iq_level_offset is dBµV. For example, if you add –26.191406 to the IQ power data, you obtain the value in dBµV, and by subtracting 107 from that, you obtain the value in dBm. The unit of reference_level is dBmV.
  
## Dataset Structure
|-- Dataset/   
|  |--IQ data.zip  
|  |  |-- Band name/  
|  |      |-- bin/  
|  |      |  |--IQ_date.bin  
|  |      |--IQ_date.json  
|  |    
|  |--npy data.zip   
|   |-- Abnormal/   
|     |-- Abnoraml_spectrogram.npy   
|   |-- Normal/   
|     |-- Normal_spectrogram.npy   
|   |-- Label/   
|     |-- Spectrum_label.csv   

* **IQ Data**: Raw IQ data (`.bin` and `.json` files) measured for each band.
* **Spectrogram Data**: Spectrogram data (`.npy` files) generated using Short Time Fourier Transform (STFT).
* **Labels**: Label data (`.csv` files) containing bounding box coordinates and Interference-to-Signal Ratio (ISR) information of anomaly signals.
* **Data Loaders**: Example jupyter notebook (`.ipynb` files) for loading the IQ data, spectrogram datas into python workspaces.
* **Anomaly Signal Generation Examples**: Example jupyter notebook (`.ipynb` files) for generating abnormal wireless signal (tone, chirp, pulse) with the fading model. The detailed process and information can be found in the paper.

## Dataset for quick evaluation (examples from each band)

* In preparation (https://huggingface.co/datasets/byungkwankim/WASD)

## Dataset Link (Whole Dataset, Google Drive)

* [**Chunk 1**](https://drive.google.com/file/d/1055_Mqq3iJJLVsYirFbKue0vz0quemtd/view?usp=drive_link)
* [**Chunk 2**](https://drive.google.com/file/d/1upenUkhVKsFYPYQg494ShImL_CmGgNYz/view?usp=drive_link)
* [**Chunk 3**](https://drive.google.com/file/d/1-7em96OKb4u4f3bOmnKWqq0iEe4bD19L/view?usp=drive_link)
* [**Chunk 4**](https://drive.google.com/file/d/1-8aqUargGx4K7RKx2O1rs-8s2_fH_AcW/view?usp=drive_link)
* [**Chunk 5**](https://drive.google.com/file/d/1-CE2wfaSP_YbT407otkhS8055aF7o4WQ/view?usp=drive_link)
* [**Chunk 6**](https://drive.google.com/file/d/1-PAfbavHwuxadLDEGF_Z-1L98mA8PON_/view?usp=drive_link)
* [**Chunk 7**](https://drive.google.com/file/d/1-PDV_f4nPDJ8e_lfiNmcwHo3THlPvyU2/view?usp=drive_link)
* [**Chunk 8**](https://drive.google.com/file/d/1-U_sTYDjCbRbm5eeK006iardzKrBWin0/view?usp=drive_link)
* [**Chunk 9**](https://drive.google.com/file/d/1-Wi8xFGUZfHc9TYjzXKi2fwf7x1m7Ohu/view?usp=drive_link)
* [**Chunk 10**](https://drive.google.com/file/d/1-_B0sLQ61jJpMn6cOZ0_IMfJ0hRTctiV/view?usp=drive_link)
* [**Chunk 11**](https://drive.google.com/file/d/1-mD1_fsuGHbCXHD1qJWSJWNJdu_-boMZ/view?usp=drive_link)
* [**Chunk 12**](https://drive.google.com/file/d/1-o3vpVnyXtH7Sn1XTrh9qWsm7YEDlYzg/view?usp=drive_link)
* [**Chunk 13**](https://drive.google.com/file/d/1-p11FzRVo39UbC3hmNvJ7kRCb3cjzpKS/view?usp=drive_link)
* [**Chunk 14**](https://drive.google.com/file/d/1-q3CHKay2m4rYgQmyqq6iri1yTxzM08M/view?usp=drive_link)
* [**Chunk 15**](https://drive.google.com/file/d/1-tBtRYcj7R8eSEEjfwogvL5LjMy_Az3i/view?usp=drive_link)
* [**Chunk 16**](https://drive.google.com/file/d/1-wrPQnoMvevT5XlLmAoMzeUeiuodpftp/view?usp=drive_link)



## Authors
Jinha Kim (jinha.kim@o.cnu.ac.kr), Hyeongwoo Kim (Hyeongwoo.kim@o.cnu.ac.kr), Byungkwan Kim(byungkwan.kim@cnu.ac.kr)

## Acknowledgements
This work was supported by the MSIT/IITP through the ICT R&D program (RS-2023-00229541).
