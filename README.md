# CS - 305 Project

Course project of team - Zero Dawn

> An attempt to improve the performance of [IPCP](https://www.cse.iitb.ac.in/~biswa/IPCP_ISCA20.pdf).

***

## Repository Overview
The directories included in this repository are,

- 600.perlbench_s-570B
- 641.leela_s-1083B
- Omnetpp
- Remove NL
- Thrash protect
- mshr_2bit
- nl threshold decrease

### 600.perlbench_s-570B
```
|
|───ipcpm.l1d_pref
|───ipcpm.l2c_pref
└───600.perlbench_s-570B_ipcpm.txt
```
### 641.leela_s-1083B
```
│
|───CPLX_degree_change
│   │───CPLX_prefetch_degree_5   
│   │───CPLX_prefetch_degree_9   
│   └───CPLX_prefetch_degree_13
│
└───mshr_2bit
    │───mshr_2bit.l1d_pref
    │───mshr_2bit.l2c_pref
    └───result.txt 
```
CPLX_degree_change folder contains the results obtained by changing the prefetch degree of CPLX class. The file names contains the prefetch degree used.
mshr_2bit folder contains modified prefetcher files for L1D and L2C caches. It also contains the result obtained for the testbench 641.leela_s-1083B


### Remove NL
This folder contains modified prefetcher files for L1D and L2C caches. It also contains the results obtained for some testbenches. Copy-paste ipcpm.l1d_pref and ipcpm.l2c_pref in prefetcher folder in champsim directory and build using the command
```
./build_champsim.sh bimodal no ipcpm ipcpm no lru 1
```
and run for a trace file using
```
./run_champsim.sh bimodal-no-ipcpm-ipcpm-no-lru-1core 10 10 $tracefile 
```
### Thrash protect
Follow the same instruction as in "Remove NL"

### mshr_2bit
This folder contains modified prefetcher files for L1D and L2C caches. It also contains the results obtained for all testbenches and a plot showing improvement. Copy-paste mshr_2bit.l1d_pref and mshr_2bit.l2c_pref in prefetcher folder in champsim directory and build using the command
```
./build_champsim.sh bimodal no mshr_2bit mshr_2bit no lru 1
```
and run for a trace file using

```
./run_champsim.sh bimodal-no-mshr_2bit-mshr_2bit-no-lru-1core 10 10 $tracefile 
```

### nl threshold decrease


```
Omnetpp/
├── baseline.txt
├── cplx_disabled
│   ├── ipcp.l1d_pref
│   └── result.txt
├── custom_nextline
│   ├── ipcp.l1d_pref
│   └── result.txt
├── degree_throttle
│   ├── ipcp.l1d_pref
│   └── result.txt
├── l2c_NL_enabled
│   ├── ipcp.l2c_pref
│   └── result.txt
├── raw_ipcp.txt
└── readme.txt
```


***
## Slides and Video

The video at this [link](https://www.youtube.com/embed/MUQfKFzIOeU) explains our approach. The files `slides.pdf` and `slides.pptx` are the slides used in this video. 


***

## Contributions

| Team Member | Roll Number | Contribution |
| --- | --- | ----------- |
| P Veda Pranav | 190050094 | Worked towards improving the performance on `605.mcf_s-994B` |
| Hardik Siloiya | 190050047 | Worked towards improving the performance on `600.perlbench_s-570B`|
| Konda Karthikeya Reddy | 190050060 | Worked towards improving the performance on `620.omnetpp_s-141B` |
| Savyasach Reddy E | 190050109 | Worked towards improving the performance on `657.xz_s-2302B` |
| Mukesh Reddy Julakanti | 190050054 | Worked towards improving the performance on `641.leela_s-1083B` |
