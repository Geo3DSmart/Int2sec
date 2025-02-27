# A Multi-Scene Roadside Lidar Benchmark towards Digital Twins of Road Intersections


This is the official implementation of the Int2sec dataset, a large-scale roadside dual-LiDAR dataset.

## Overview
- [Data Download](#Data-Download)
- [Benchmark](#Benchmark)
  - [3D Object Detection](#3D-Object-Detection)
  - [Semi-supervised Object Detection](#Semi-supervised-Object-Detection)
  - [3D Object Tracking](#3D-Object-Tracking)
  - [Moving Object Segmentaton](#Moving-Object-Segmentaton)
- [Acknowledgment](#Acknowledgment)

## Data Download
Our dataset is freely available to researchers. Please download and sign our [agreement](https://docs.google.com/document/d/14ufBczTjLYnxm5bWkFROsz9FYEugZ2QL/edit?usp=sharing&ouid=110390481963822269546&rtpof=true&sd=true) and send it to the provided email address (wen.xiao@cug.edu.cn). You will receive the download link within one week.
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

### 3D Object Detection

#### Results of detection models on the Int2sec-D validation set.
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

#### Results of detection models on the Int2sec-D test set.
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

### Semi-supervised Object Detection

#### Results of semi-supervised detection models on the Int2sec-S validation set.

<table>
    <tr>
        <th rowspan="2">Method</th>
        <th colspan="4">Vehicle (AP@50)(%)</th>
        <th colspan="4">Pedestrian (AP@50)(%)</th>
        <th colspan="4">Cyclist (AP@50)(%)</th>
        <th rowspan="2">mAP(%)</th>
    </tr>
    <tr>
        <th>overall</th> <th>0-30m</th> <th>30-50m</th> <th>50m-inf</th>
        <th>overall</th> <th>0-30m</th> <th>30-50m</th> <th>50m-inf</th>
        <th>overall</th> <th>0-30m</th> <th>30-50m</th> <th>50m-inf</th>
    </tr>
    <tr><td colspan="14" align="center"><b>1%</b></td></tr>
    <tr>
        <td>CoIn</td> <td>33.55</td> <td>66.25</td> <td>36.7</td> <td>15.22</td>
        <td>7.59</td> <td>11.24</td> <td>9.86</td> <td>2.93</td>
        <td>2.68</td> <td>5.19</td> <td>2.39</td> <td>0.38</td> <td>14.6</td>
    </tr>
    <tr>
        <td>HINTED</td> <td>45.57</td> <td>72.8</td> <td>49.78</td> <td>28.59</td>
        <td>18.57</td> <td>25.81</td> <td>21.66</td> <td>10.79</td>
        <td>13.18</td> <td>25.08</td> <td>12.79</td> <td>4.79</td> <td>25.77</td>
    </tr>
    <tr><td colspan="14" align="center"><b>10%</b></td></tr>
    <tr>
        <td>CoIn</td> <td>58.54</td> <td>81.67</td> <td>68.63</td> <td>42.94</td>
        <td>41.45</td> <td>62.99</td> <td>44.95</td> <td>20.27</td>
        <td>61.62</td> <td>87.53</td> <td>62.57</td> <td>31.84</td> <td>53.87</td>
    </tr>
    <tr>
        <td>HINTED</td> <td>60.97</td> <td>81.49</td> <td>66.36</td> <td>46.76</td>
        <td>45.24</td> <td>60.82</td> <td>49.79</td> <td>26.24</td>
        <td>70.21</td> <td>87.6</td> <td>72.05</td> <td>46.03</td> <td>58.81</td>
    </tr>
    <tr><td colspan="14" align="center"><b>20%</b></td></tr>
    <tr>
        <td>CoIn</td> <td>63.95</td> <td>84.68</td> <td>72.43</td> <td>48.92</td>
        <td>54.15</td> <td>74.3</td> <td>58.01</td> <td>32.81</td>
        <td>68.15</td> <td>92.39</td> <td>71.83</td> <td>40.67</td> <td>62.08</td>
    </tr>
    <tr>
        <td>HINTED</td> <td>66.12</td> <td>83.38</td> <td>74.16</td> <td>52.82</td>
        <td>55.64</td> <td>70.73</td> <td>60.85</td> <td>36.77</td>
        <td>73.94</td> <td>86.37</td> <td>76.17</td> <td>59.85</td> <td>65.23</td>
    </tr>
</table>

#### Results of semi-supervised detection models on the Int2sec-S test set.

<table>
    <tr>
        <th rowspan="2">Method</th>
        <th colspan="4">Vehicle (AP@50)(%)</th>
        <th colspan="4">Pedestrian (AP@50)(%)</th>
        <th colspan="4">Cyclist (AP@50)(%)</th>
        <th rowspan="2">mAP(%)</th>
    </tr>
    <tr>
        <th>overall</th> <th>0-30m</th> <th>30-50m</th> <th>50m-inf</th>
        <th>overall</th> <th>0-30m</th> <th>30-50m</th> <th>50m-inf</th>
        <th>overall</th> <th>0-30m</th> <th>30-50m</th> <th>50m-inf</th>
    </tr>
    <tr><td colspan="14" align="center"><b>1%</b></td></tr>
    <tr>
        <td>CoIn</td> <td>34.3</td> <td>65.69</td> <td>38.31</td> <td>15.5</td>
        <td>7.27</td> <td>11.01</td> <td>8.75</td> <td>2.91</td>
        <td>2.98</td> <td>5.25</td> <td>3.27</td> <td>0.57</td> <td>14.85</td>
    </tr>
    <tr>
        <td>HINTED</td> <td>45.5</td> <td>72.68</td> <td>51.8</td> <td>27.48</td>
        <td>18.6</td> <td>25.85</td> <td>21.32</td> <td>10.36</td>
        <td>14.15</td> <td>26</td> <td>12.5</td> <td>5.4</td> <td>26.08</td>
    </tr>
    <tr><td colspan="14" align="center"><b>10%</b></td></tr>
    <tr>
        <td>CoIn</td> <td>60.47</td> <td>82.06</td> <td>69.17</td> <td>42.63</td>
        <td>42.19</td> <td>63.93</td> <td>46.27</td> <td>19.4</td>
        <td>61.91</td> <td>86.37</td> <td>65.65</td> <td>31.78</td> <td>54.85</td>
    </tr>
    <tr>
        <td>HINTED</td> <td>62.50</td> <td>81.73</td> <td>68.36</td> <td>46.22</td>
        <td>44.01</td> <td>59.63</td> <td>48.23</td> <td>24.98</td>
        <td>69.62</td> <td>86.22</td> <td>74.17</td> <td>45.27</td> <td>58.71</td>
    </tr>
    <tr><td colspan="14" align="center"><b>20%</b></td></tr>
    <tr>
        <td>CoIn</td> <td>63.99</td> <td>84.73</td> <td>74.12</td> <td>49.06</td>
        <td>54.23</td> <td>75.88</td> <td>57.68</td> <td>31.87</td>
        <td>68.17</td> <td>91.89</td> <td>72.27</td> <td>41.33</td> <td>62.13</td>
    </tr>
    <tr>
        <td>HINTED</td> <td>67.46</td> <td>83.64</td> <td>74.11</td> <td>53.16</td>
        <td>55.72</td> <td>71.03</td> <td>59.26</td> <td>36.83</td>
        <td>74.01</td> <td>86.48</td> <td>77.23</td> <td>58.32</td> <td>65.73</td>
    </tr>
</table>

### 3D Object Tracking

#### Results of 3D Object Tracking models on the Int2sec-S validation set.

<table>
    <tr>
        <th>Tracking</th>
        <th>Detection</th>
        <th>AMOTA (%)</th>
        <th>AMOTP (m)</th>
    </tr>
    <tr>
        <td rowspan="3">PC-TCNN</td>
        <td>IA-SSD</td>
        <td>56.4</td>
        <td>0.825</td>
    </tr>
    <tr>
        <td>PV-RCNN</td>
        <td>50.9</td>
        <td>0.801</td>
    </tr>
    <tr>
        <td>CenterPoint</td>
        <td>41.3</td>
        <td>0.900</td>
    </tr>
</table>

#### Results of 3D Object Tracking models on the Int2sec-S test set.

<table>
    <tr>
        <th>Tracking</th>
        <th>Detection</th>
        <th>AMOTA (%)</th>
        <th>AMOTP (m)</th>
    </tr>
    <tr>
        <td rowspan="3">PC-TCNN</td>
        <td>IA-SSD</td>
        <td>65.6</td>
        <td>0.661</td>
    </tr>
    <tr>
        <td>PV-RCNN</td>
        <td>54.7</td>
        <td>0.714</td>
    </tr>
    <tr>
        <td>CenterPoint</td>
        <td>43.8</td>
        <td>0.797</td>
    </tr>
</table>

### Moving Object Segmentaton

#### Results of Moving Object Segmentaton models on the Int2sec-S test set.

<table>
  <thead>
    <tr>
      <th rowspan="2">Method</th>
      <th colspan="2">Int2sec-S</th>
    </tr>
    <tr>
      <th>IoU Moving</th>
      <th>IoU Static</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>MotionSeg3D</td>
      <td>0.662</td>
      <td>0.977</td>
    </tr>
    <tr>
      <td>LMNet</td>
      <td>0.678</td>
      <td>0.979</td>
    </tr>
    <tr>
      <td>4DMOS</td>
      <td>0.669</td>
      <td>0.983</td>
    </tr>
  </tbody>
</table>

#### Results of Moving Object Segmentaton models on the Int2sec-D test set.

<table>
  <thead>
    <tr>
      <th rowspan="2">Method</th>
      <th colspan="2">Int2sec-D</th>
    </tr>
    <tr>
      <th>IoU Moving</th>
      <th>IoU Static</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>MotionSeg3D</td>
      <td>0.660</td>
      <td>0.978</td>
    </tr>
    <tr>
      <td>LMNet</td>
      <td>0.382</td>
      <td>0.944</td>
    </tr>
    <tr>
      <td>4DMOS</td>
      <td>0.656</td>
      <td>0.981</td>
    </tr>
  </tbody>
</table>


## Acknowledgment
- [OpenPCDet](https://github.com/open-mmlab/OpenPCDet)
- [SUSTechPOINTS](https://github.com/naurril/SUSTechPOINTS)

Sincere appreciation for their great contributions.
