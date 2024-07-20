# Case-Study: Parallel Processing and Multicore Processors

## Introduction

## Literature Review

## Analysis

## Application

## Conclusion

## References:

Possible References and Notes: 

### 1. https://www2.eecs.berkeley.edu/Pubs/TechRpts/2006/EECS-2006-183.pdf

This study focuses on the evolutionary approach to parallel hardware and software. The general belief is that it way work for 2 - 8 core systems, but is likely to reach diminishing returns at 16 or 32 core systems, if the general conventiion of doubling the number of cores per silicone generation is followed. This is following the convention set by instruction-level parallelism

This study follows 7 major questions, the most important of which are as follows:

[-] Ease of writing programs on parallel processing systems

[-] Efficiency calculated through MIPS(Million Instructions per Second) per Watt, per Area of Silicone and per Development Dollar

[-] Maximizing programmer productivity through human-centric design, rather than the conventional focus on hardware or applications  

[-] Functionality should be tested and orchestrated through libraries and virtual machines


### 2. https://www.youtube.com/watch?v=q7sgzDH1cR8

### 3. https://www.youtube.com/watch?v=IZfWjg3U3mA&t=357s

### 4. https://web.archive.org/web/20111125035151/http://www.csa.com/discoveryguides/multicore/review.pdf

### 5. https://ijret.org/volumes/2015v04/i09/IJRET20150409015.pdf

This study largely focuses on the technology of multicore processor technology itself, as well as real-world use case issues regarding power, temperature and interconnectivity issues and the addition of more cores. T

This study should ideally be referenced in the introduction.

Things to make note of:

It specifies that the cores need to be on a single die

"The key factor about 
multicore processor is that it gives the same performance of 
a single faster processor at lower power dissipation and at a 
lower clock frequency by handling more tasks or 
instructions in parallel."

The performance of a 
processor is a function of three major factors, which 
includes IPC (instructions per cycle), CPI (clock cycles per 
instruction) and clock cycle (or clock frequency)

Multicore processors work on multiple 
instructions and multiple data. Multiple cores execute 
multiple threads (multiple processes/instructions) while 
using different parts of memory (multiple data). This 
enhances TLP. The main memory is shared by all cores. 
Each core is associated with its own cache and they all share 
the system bus

Picture with explanation is likely necessary 

![image](https://github.com/user-attachments/assets/59169b8a-a668-4642-ad68-a338d99e2b21)

Multicore technology uses homogeneous 
and heterogeneous cores. In homogeneous configuration, all 
the cores are identical and each core has same hardware. 
These cores use divide and rule approach for improving the 
performance by dividing a more complex application into 
less complex applications and execute them simultaneously. 
There are many other benefits of this approach such as 
reusability, simpler design etc.[1]
In heterogeneous cores, there are dedicated application 
specific cores that work on specialized applications. For 
example a system comprising of a DSP core that handles a 
multimedia application requiring intensive mathematical 
computations, while other cores handle some other 
applications simultaneously. Heterogeneous core is more 
complex, but has its own benefits also. Multicore Processors 
sometimes take advantage of both homogeneous and 
heterogeneous configurations to improve performance

The performance of a multicore processor strongly depends 
on the design of algorithm or application which is governed 
by Amdahl’s Law. This law was given by Geve Amdahl, a 
computer architect. This law is used to compute the 
theoretical maximum speed with multiple processors in 
parallel computing. This law states that the speed of a 
process in parallel computing is limited by the time needed 
for the sequential part of the process. For example , if a 
process requires X hours to complete on a single core, and a 
portion of the process that takes Y hours to execute which 
can not be parallelized, while remaining (X-Y) hours can be 
parallelized, then regardless of the number of processors, 
the minimum time required for the execution can not be less 
then (X-Y) hours

The good processing speed of the multicore processors is 
due to the multiple cores which operate simultaneously on 
instructions, at lower frequency than the single core. At the 
same clock frequency, the multicore processor will process 
more data than the single core processor. In addition to this, 
multicore processors deliver high performance and handle 
complex tasks at a comparatively lower energy or lower 
power as compared with a single core, which is crucial 
factor in appliances such as mobile phones, laptop etc. 
which operate on batteries. Also, since the cores are 
fabricated close to each other on the same chip, the signals 
travel shorter distance between them due to which there is 
less attenuation of signals. Since the signals don’t attenuate 
much, more data is transferred in a given time and there is 
no need of repeating the signals

The study further talks about heat and power issues, marking them as disadvantages for parallel processing versus single core. The advantages seem to largely outnumber the disadvantages

The architecture of the core must be such that the 
amount of heat generated in the chip is well distributed 
across the chip. The power consumption is also a 
function of number of transistors on a chip. When 
more cores are added, the transistor density also 
increases which contributes to the power consumption

To reduce the unnecessary power consumption, the 
power management unit has to turn off or shut down 
the cores which don’t operate at times or the cores that 
are not required at times. Also, the cores run at a 
comparatively lower frequency than a single processor 
to reduce the power dissipation

To achieve a high level of parallelism and an overall 
high performance, software developers must write such 
algorithms that can take full advantage of multicore 
design. In other words, all the cores should be used in 
the most efficient manner. If the algorithms written are 
not compatible with the multicore design, then it may 
happen that one or more cores starve for data. In such a 
case, the process will run on one of the cores, while 
other cores will sit idle. So, in a nutshell, the success of 
multicore technology strongly depends on the way the 
algorithms are written.

These snippets sum up the most important points of the study

