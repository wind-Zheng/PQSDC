# PQSDC
![made-with-C++](https://img.shields.io/badge/Made%20with-C++11-brightgreen)
![made-with-OpenMP](https://img.shields.io/badge/Made%20with-OpenMP-blue)

<!-- LOGO -->
<br />
<h1>
<p align="center">
  <img src="https://github.com/fahaihi/PMFFRC/blob/master/Log.png" alt="Logo" width="722" height="189">
</h1>
  <p align="center">
   A partition-parallel predictive mapping tool for improved DNA quality score compression.
    </p>
</p>
<p align="center">
  <a href="#about-the-pmffrc">About The Pqsdc</a> •
  <a href="#copy-our-project">Copy Our Project</a> •
  <a href="#useage">Useage</a> •
  <a href="#example">Example</a> •
  <a href="#our-experimental-configuration">Our Experimental Configuration</a> •
    <a href="#dataset-acquisition">Dataset Acquisition</a> •
  <a href="#aknowledgements">Acknowledgements</a> •
</p>  

<p align="center">
  
![screenshot](img/clip.gif)
</p>                                                                                                                             
      
## About The PQSDC
The PQSDC takes QSD compression rate, time and memory overhead as the overall optimization goal, based on the parallel sequence partition model and run-length prediction mapping model, by combining optimization technologies such as SIMD, multi-threading, cluster parallelism, memory buffer, thread binding and memory alignment, In this way, we look forward to developing a domestic open source large-scale high-throughput genome quality score data lossless compressor.

## Copy Our Project

firstly, clone our tools from GitHub:
```sh
git clone https://github.com/wind-Zheng/PQSDC.git
```
secondly, turn to PQSDC directory：
```sh
cd PQSDC
```
finally, Run the following command：
```
bash install.sh
```
In addition, we need to configure the operating environment of zpaq,turn to zpaq-master directory:
```
cd zpaq-master
```
Then,makefile:
```
make
```

## Usage
To run `./PQSDC`, just need to execute script`PQSDC/pqsdc_v1.sh` 
run `./pqsdc_v1.sh` with the following command:
```sh
  ./pqsdc_v1.sh [mode] [fileName] [threads]
  [mode]        -c Compression
                -d DECompression
  [fileName]    multi-fastQ-files-path    
  [threads]     num_threads. --Default=20
```

## Examples
1、Compress multiple files in the /userdir/data/test.quality ：
```sh
./pqsdc_v1.sh c /userdir/data/test.quality 20 
```
2、DeCompress the /userdir/data/test.quality.partition file using 20 CPU :
```sh
./pqsdc_v1.sh d /userdir/data/test.quality.partition 20
```
3、Print help information:
```sh
./PMFFRC -h
```

## Our Experimental Configuration
Our experiment was conducted on the Dawning 7000A supercomputer system at the Nanning Branch of the National Supercomputing Center, using a queue of CPU/GPU heterogeneous computing nodes. The compute nodes used in the experiment were configured as follows: 
  2\*Intel Xeon Gold 6230 CPU (2.1Ghz, total 40 cores), 
  2\*NVIDIA Tesla-T4 GPU (16GB of cuda memory, 2560 CUDA cores), 
  512GB DDR4 memory, and 
  8\*900GB external storage.
 
 

## Acknowledgements
- Thanks to [@HPC-GXU](https://hpc.gxu.edu.cn) for the computing device support.   
- Thanks to [@NCBI](https://www.freelancer.com/u/Ostokhoon) for all available datasets.

## Additional Information
**Version：**    V1.2023.06.16.
**Authors:**     NBJL-BioGrop.
**Contact us:**  https://nbjl.nankai.edu.cn OR zhengyf@nbjl.nankai.edu.cn
