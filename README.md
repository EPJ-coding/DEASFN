# Dilated Evolving Attentive Spatial-Frequency Network
    Seeing the Unseen: 
    Wifi-based 2D Human Pose Estimation via Dilated Evolving Attentive Spatial-Frequency Network


* [Architecture](#architecture)

* [Dataset](#dataset)

* [Usage](#usage)

* [Visulization](#visulization)

* [Result](#result)

* [Reference](#reference)


## Architecture
![image](https://github.com/DEASFN/DEASFN/blob/master/pic/architecture.png)

## Dataset

<table>
    <tr>
        <td colspan="3" align="center">GPE</td> 
        <td colspan="3" align="center">SPE</td> 
   </tr>
    <tr>
        <td align="center"># Person</td>
        <td align="center">Number</td>
        <td align="center">Url</td>
        <td align="center">Action</td>
        <td align="center">Number</td>
        <td align="center">Url</td>
    </tr>
    <tr>
        <td align="center">1</td>
        <td align="center">12,884</td>
        <td align="center">https://reurl.cc/EzXD8R</td>
        <td align="center">Walk</td>
        <td align="center">78,852</td>
        <td align="center">https://reurl.cc/OqEL9D</td>
    </tr>
    <tr>
        <td align="center">2</td>
        <td align="center">18,879</td>
        <td align="center">https://reurl.cc/ygmX1a</td>
        <td align="center">Wave</td>
        <td align="center">77,431</td>
        <td align="center">https://reurl.cc/Z71vGQ</td>
    </tr>
    <tr>
        <td align="center">3</td>
        <td align="center">27,694</td>
        <td align="center">https://reurl.cc/e8Wa5W</td>
        <td align="center">Jump</td>
        <td align="center">40,670</td>
        <td align="center">https://reurl.cc/j5RYNM</td>
    </tr>
    <tr>
        <td align="center">>=4</td>
        <td align="center">28,178</td>
        <td align="center">https://reurl.cc/m9ZXd7</td>
        <td align="center">Run</td>
        <td align="center">41,238</td>
        <td align="center">https://reurl.cc/EzXL3m</td>
    </tr>
    <tr>
        <td align="center"><b>Total</b></td>
        <td align="center"><b>87,635</b></td>
        <td align="center">X</td>
        <td align="center"><b>Total</b></td>
        <td align="center"><b>238,191</b></td>
        <td align="center">X</td>
    </tr>
    
</table>


## Usage

#### Install
````
$ git clone https://github.com/DEASFN/DEASFN.git
````

#### Setup
* create the virtual enciorment
````
$ cd DEASFN/
$ python3 -m venv env
````
* activate the virtual environment
````
$ source env/bin/activate
````
* install the necessary packages
````
$ pip install -r requirements.txt
````
If there are errors about _gdown_ package, you can ignore them.

#### Download the dataset
* Download SPE _or_ GPE dataset
````
$ chmod +x download_SPE.sh     or     $ chmod +x download_GPE.sh     
$ ./download_SPE.sh     or     $ ./download_GPE.sh
````
When you find the download has exited, you need to press `ctrl+c` to terminate the sh file by yourself. 

If errors occur, you can download by yourself using the links provided above.

Please make sure that all four zipfiles in `DEASFN/dataset/SPE` _or_ `DEASFN/dataset/GPE`.

* unzip the dataset ( You can substitute `GPE` for `SPE`)
````
$ cd DEASFN/dataset/SPE
$ chmod +x SPE.sh
$ ./SPE.sh
````

#### Train
You can adjust the training parameters in `config/args.py`
````
$ python3 TrainDeasfn.py--dataset=SPE     or     $ python3 TrainDeasfn.py --dataset=GPE
````
#### Test
You can adjust the testing parameters in `config/args.py`
````
$ python3 TestDeasfn.py --dataset=SPE     or     $ python3 TestDeasfn.py --dataset=GPE
````
## Visulization
#### Comparative visualization of DEASFN and two models (PIW[2] and WiSPPN[1])
![image](https://github.com/DEASFN/DEASFN/blob/master/pic/comparison.png)

#### Some positive cases of DEASFN on our two benchmarks
![image](https://github.com/DEASFN/DEASFN/blob/master/pic/demo.png)

#### Comparative GIF images of DEASFN and two models (PIW[2] and WiSPPN[1]) for each action
<table>
    <tr>
        <td align="center"></td> 
        <td align="center">DEASFN</td> 
        <td align="center">PIW</td>
        <td align="center">WiSPPN</td>
   </tr>
    <tr>
        <td align="center">Walk</td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/walk.gif"></td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/walk_PIW.gif"></td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/walk_wisppn.gif"></td>
    </tr>
    <tr>
        <td align="center">Wave</td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/wave.gif"></td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/wave_PIW.gif"></td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/wave_wisppn.gif"></td>
    </tr>
    <tr>
         <td align="center">Jump</td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/jump.gif"></td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/jump_PIW.gif"></td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/jump_wisppn.gif"></td>
   </tr>
    <tr>
        <td align="center">Run</td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/run.gif"></td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/run_PIW.gif"></td>
        <td align="center"><img src="https://github.com/DEASFN/DEASFN/blob/master/pic/run_wisppn.gif"></td>
    </tr>
</table>


#### Comparative visualization of DEASFN and camera-based method(Openpose)
From this comparison, we can easily observe that DEASFN is better than the camera-based method in dark environment.  Under poor illumination, Openpose is likely to loss some keypoints, such as wrist, ankle, and so forth. However, DEASFN can correctly return all keypoints.
|**DEASFN**|Openpose|                       
| :------:| :------: |
|![image](https://github.com/DEASFN/DEASFN/blob/master/pic/DEASFN2.gif)|![image](https://github.com/DEASFN/DEASFN/blob/master/pic/openpose2.gif)|


## Result
* **Comparisons on the proposed benchmarks:**

<table>
    <tr>
        <td align="center">Metric</td> 
        <td align="center">Benchmark</td> 
        <td align="center">WiSPPN[1]</td> 
        <td align="center">PIW[2]</td> 
        <td align="center"><b>DEASFN</b></td> 
   </tr>
    <tr>
        <td align="center" rowspan='2'>MPJPE</td>
        <td align="center">SPE</td>
        <td align="center">44.16</td>
        <td align="center">78.88</td>
        <td align="center"><b>37.34</b></td>
    </tr>
    <tr>
        <td align="center">GPE</td>
        <td align="center">X</td>
        <td align="center">119.60</td>
        <td align="center"><b>44.14</b></td>
    </tr>
    <tr>
        <td align="center" rowspan='2'>PCK@20</td>
        <td align="center">SPE</td>
        <td align="center">21.86%</td>
        <td align="center">32.96%</td>
        <td align="center"><b>50.05%</b></td>
    </tr>
    <tr>
        <td align="center">GPE</td>
        <td align="center">X</td>
        <td align="center">27.64%</td>
        <td align="center"><b>43.98%</b></td>
    </tr>
</table>

* **Comparative results against other methods on our SPE benchmark (PCK@20):**

|Action|WiSPPN|PIW|**DEASFN**|                       
| :------:| :------: | :------: | :------: |
|Walk|23.58%|39.87%|**61.14%**|
|Wave|25.92%|33.06%|**45.81%**|
|Jump|22.12%|37.91%|**58.11%**|
|Run|15.82%|20.99%|**35.15%**|


* **Comparative results against other methods on our GPE benchmark (PCK@20):**

|# Person|PIW|**DEASFN**|                       
| :------:| :------: | :------: |
|1-person|53.37%|**72.65%**|
|2-person|49.31%|**65.39%**|
|3-person|19.54%|**34.75%**|
|>=4 person|22.66%|**39.12%**|

* **Ablation study on our SPE benchmark:**

|Model|Architecture|PCK@20|                       
| :------:| :------| :------: |
|1|SFN|44.99%|
|2|ASFN|45.95%|
|3|DEASFN, D=1|48.08%|
|**4**|**DEASFN, D=3 (Proposed)**|**50.05%**|
|5|DEASFN, D=5|45.95%|



## Reference
* [1] Fei Wang, Stanislav Panev, Ziyi Dai, Jinsong Han, and Dong Huang. 2019. Can wifi estimate person pose?arXiv preprint arXiv:1904.00277(2019).
* [2] Fei Wang, Sanping Zhou, Stanislav Panev, Jinsong Han, and Dong Huang. 2019.Person-in-WiFi: Fine-grained person perception using WiFi. InProceedings of theIEEE International Conference on Computer Vision. 5452–5461.
