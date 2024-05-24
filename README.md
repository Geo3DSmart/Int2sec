# A Multi-Scene Roadside Lidar Benchmark towards Digital Twins of Road Intersections


This is the official implementation of ISPRS TCIV 2024 paper. "A Multi-Scene Roadside Lidar Benchmark towards Digital Twins of Road Intersections".

**Miao Tang, Dianyu Yu, Peiguang Li, Chengwen Song, Pu Zhao, Wen Xiao, Nengcheng Chen**



## Overview
- [Data Download](#data-download)
- [Benchmark](#benchmark)
- [Citation](#citation)
- [Acknowledgment](#acknowledgment)

## Data Download
Our dataset is freely available to researchers. Please download and sign our [agreement](https://drive.google.com/file/d/1uGB5JPkyqn4XfyuBXjwIsZ1jqTgHRYnm/view) and send it to the provided email address (yudianyu@outlook.com). You will receive the download link within one week.
After downloading the data, please put the data in the following structure:
```shell
├── Int2sec-S-dataset
│   ├── 0011
|      |── label
|      |── lidar
|      |── metadata.json
│   ├── 0012
│   ├── 0021
│   ├── 0022
│   ├── ...
├── Int2sec-D-dataset
│   ├── 001
|      |── Lidar1
|         |── label
|         |── lidar
|         |── metadata.json
|      |── Lidar2
|         |── label
|         |── lidar
|         |── metadata.json
|      |── metadata.json
│   ├── 002
│   ├── 003
│   ├── ...
```


## Benchmark


### Evaluation results of our model and baseline models on the Int2sec-D test set
<table>
  <tr>
    <th>Method</th>
    <th colspan="4">Vehicle (AP@50)(%)</th>
    <th colspan="4">Pedestrian (AP@50)(%)</th>
    <th colspan="4">Cyclist (AP@50)(%)</th>
    <th>mAP(%)</th>
  </tr>
  <tr>
    <th></th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th></th>
  </tr>
  <tr>
    <td>IA-SSD</td>
    <td>28.34</td>
    <td>78.22</td>
    <td>31.61</td>
    <td>14.67</td>
    <td>17.94</td>
    <td>24.53</td>
    <td>13.90</td>
    <td>11.66</td>
    <td>20.11</td>
    <td>31.30</td>
    <td>11.30</td>
    <td>13.33</td>
    <td>22.13</td>
  </tr>
  <tr>
    <td>PV-RCNN</td>
    <td>26.84</td>
    <td>75.64</td>
    <td>30.12</td>
    <td>13.40</td>
    <td>16.07</td>
    <td>32.38</td>
    <td>8.15</td>
    <td>10.94</td>
    <td>21.84</td>
    <td>50.89</td>
    <td>15.40</td>
    <td>2.91</td>
    <td>21.58</td>
  </tr>
  <tr>
    <td>CenterPoint</td>
    <td>22.05</td>
    <td>67.23</td>
    <td>21.58</td>
    <td>12.29</td>
    <td>27.84</td>
    <td>44.38</td>
    <td>13.91</td>
    <td>25.64</td>
    <td>14.45</td>
    <td>30.11</td>
    <td>14.34</td>
    <td>2.32</td>
    <td>21.45</td>
  </tr>
</table>


### valuation results of our model and baseline models on the Int2sec-D validation set
<table>
  <tr>
    <th>Method</th>
    <th colspan="4">Vehicle (AP@50)(%)</th>
    <th colspan="4">Pedestrian (AP@50)(%)</th>
    <th colspan="4">Cyclist (AP@50)(%)</th>
    <th>mAP(%)</th>
  </tr>
  <tr>
    <th></th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th></th>
  </tr>
  <tr>
    <td>IA-SSD</td>
    <td>34.38</td>
    <td>80.95</td>
    <td>39.43</td>
    <td>16.59</td>
    <td>14.66</td>
    <td>27.28</td>
    <td>15.43</td>
    <td>4.66</td>
    <td>24.82</td>
    <td>39.62</td>
    <td>23.31</td>
    <td>11.83</td>
    <td>24.62</td>
  </tr>
  <tr>
    <td>PV-RCNN</td>
    <td>31.17</td>
    <td>74.18</td>
    <td>34.77</td>
    <td>15.77</td>
    <td>8.92</td>
    <td>13.88</td>
    <td>10.72</td>
    <td>4.73</td>
    <td>24.84</td>
    <td>42.30</td>
    <td>20.91</td>
    <td>11.76</td>
    <td>21.64</td>
  </tr>
  <tr>
    <td>CenterPoint</td>
    <td>26.93</td>
    <td>70.16</td>
    <td>20.62</td>
    <td>17.86</td>
    <td>12.36</td>
    <td>23.03</td>
    <td>11.85</td>
    <td>4.29</td>
    <td>25.31</td>
    <td>41.80</td>
    <td>22.64</td>
    <td>12.34</td>
    <td>21.54</td>
  </tr>
</table>


## Citation
If you find Int2sec useful in your research or applications, please consider giving us a star 🌟 and citing it by the following BibTeX entry.
```shell
@article{tang2024int2sec,
  title={A Multi-Scene Roadside Lidar Benchmark towards Digital Twins of Road Intersections},
  author={Miao Tang, Dianyu Yu, Peiguang Li, Chengwen Song, Pu Zhao, Wen Xiao, Nengcheng Chen},
  booktitle={ISPRS TCIV 2024},
  year={2024}
}
```

## Acknowledgment
- [OpenPCDet](https://github.com/open-mmlab/OpenPCDet)
- [SUSTechPOINTS](https://github.com/naurril/SUSTechPOINTS)

Sincere appreciation for their great contributions.
