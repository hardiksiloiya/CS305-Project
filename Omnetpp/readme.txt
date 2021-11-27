This folder contains the efforts for improving the omnetpp benchmark
The individual folders contains the changed files as per the name of folders
In order to reproduce , just replace the respective files in champsim and run

The custom nextline is included with adjusting degree scheme. The NL prefetching part is modified in a way not to 
prefetch next line if current line is accessed by some CPLX IP in the past . Unfortunately it never get's triggered
The block number storing table get's overwritten very frequently and this condition never triggers. Resulting it being USELESS


Other efforts include various Next line prefetching schemes such as disabling it completely and issuing it only when cur_block is accessed by some 
GS or CPLX ip in the past. Some of these have less improvement than raw ipcp, but better than baseline still.
