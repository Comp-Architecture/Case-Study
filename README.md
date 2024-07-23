# Case-Study: Parallel Processing and Multicore Processors

## Introduction

Multicore processors are a parallel computing architecture which consists of at least two or more cores that read and write CPU instructions on a single chip. 

The main feature of these processors is their ability to run multiple instructions at the same time, which can decrease the amount of time needed to execute programs when compared to single-core processors, which run instructions one at a time. While single-core processors can have higher core performance, applications optimized for parallel processing will have an overall faster result. 

This approach, however, is theorized to have diminishing returns. According to Moore’s Law, the number of cores on a chip would double once every 18 months when looking at the general progression of this technology(successive silicone generations), however, it is largely believed that while it is extremely beneficial when comparing the differences between each of the earlier generations, such as dual and quad-core, diminishing returns are expected around 8 and 16 more cores.

The goal of this paper is to take a look into multi-core processor technology, understand its impact and evolution, and identify the practical need and application for this technology, as well as its advantages and limitations.

## Literature Review

The studies on parallel hardware and software investigates evolutionary approaches, highlighting their effectiveness for systems with 2-8 cores but noting potential diminishing returns when scaling to 16 or 32 cores. 

This is in line with instruction-level parallelism and reflects the industry's trend of doubling cores per silicon generation. Key areas of focus include ease of programming for parallel systems, efficiency metrics (measured in Million Instructions per Second or MIPS, per Watt, per area of silicon, and per development dollar), and strategies to enhance programmer productivity through human-centric design. It also underscores the importance of testing and orchestrating functionality via libraries and virtual machines for optimal system performance.

In multi-processing operating systems, two or more CPUs within a single computer share core components like the bus and RAM, enabling simultaneous task execution. This arrangement effectively doubles processing speed compared to a single-processor system. Multi-processing systems are categorized into:
- Symmetric Multiprocessing (SMP): All CPUs are equally connected, allowing any CPU to handle any command and access all system components, including ROM, RAM, and peripherals. A single operating system manages all CPUs, but this can lead to complex connection networks and increased production costs due to simultaneous hardware access by multiple CPUs.
- Asymmetric Multiprocessing (AMP): AMP features a hierarchical structure where one "leader" CPU assigns tasks to subordinate processors and manages communication with hardware. Secondary processors enhance overall processing speed by executing tasks on behalf of the primary CPU.

The advantages of multi-processing include increased throughput through simultaneous task handling, enhanced system reliability (since other processors continue to function if one fails), cost savings by consolidating CPU power into a single system, and improved parallel processing capabilities.

The history of microprocessors is significantly influenced by Moore's Law, proposed in 1965, which initially predicted that the number of transistors on a processor would double each year. This was revised in 1975 to a doubling every two years, with David House later estimating performance doubling every 1.5 years. However, as processor frequencies reached a plateau, these predictions required adjustment.

To address performance limits, multi-core processors have been developed, typically operating at lower frequencies than single-core processors. This design reduces the stress on each core while maintaining efficiency. For example, increasing a single-core processor's clock frequency by 20% results in only a 13% performance gain but requires 73% more power. Conversely, reducing the clock frequency by 20% decreases power usage by 49% with only a 13% performance loss. Adding a second core to a single-core system can provide a 73% performance increase while maintaining similar power consumption.

The Intel's Pentium 4 exemplified this evolution with frequencies ranging from 1.3 to 3.8 GHz. Despite increasing chip size and transistor count, heat dissipation became a significant challenge. 

Techniques such as the superscalar process enable simultaneous issuance of multiple instructions, pre-fetching, and out-of-order execution. Branch prediction methods help manage branch instructions, and additional techniques like loop unrolling, neural network-based predictors, register renaming, trace caches, reorder buffers, dynamic/software scheduling, and data value prediction contribute to performance enhancements.

Focusing specifically on multicore processors, the studies explore practical issues like power consumption, temperature management, and interconnectivity as more cores are added. Notably, multicore processors require cores to be on a single die. A key advantage is their ability to deliver the performance of a faster single-core processor at lower power dissipation and clock frequency by handling more tasks in parallel. Processor performance is influenced by IPC (instructions per cycle), CPI (clock cycles per instruction), and clock frequency.

Multicore processors enhance thread-level parallelism (TLP) by executing multiple instructions and handling multiple data streams simultaneously. While the main memory is shared, each core has its own cache, and all cores share the system bus. Two configurations for multicore technology include:
- Homogeneous Cores: All cores are identical, sharing the same hardware, improving performance by dividing complex tasks into simpler ones that can be executed simultaneously. Benefits include reusability and a simpler design.
- Heterogeneous Cores: This configuration involves specialized cores dedicated to specific applications, such as a DSP core for multimedia tasks. Although more complex, it offers significant performance benefits for specialized tasks. Many multicore processors combine both homogeneous and heterogeneous cores to enhance overall performance.

Performance is also influenced by Amdahl's Law, which states that parallel computing speed is limited by the sequential portion of the process, highlighting the theoretical maximum speedup achievable with multiple processors. While multicore processors operate at lower frequencies to reduce power consumption and heat generation, their close core fabrication minimizes signal attenuation, allowing for efficient data transfer.

“Using absolute execution times, Amdahl's law is in terms of `T_after`, the execution time after an improvement; `T_improved`, the execution time affected by the improvement; `S`, how many times faster the improved part runs, or its speedup; and `T_unaffected`, the execution time unaffected by the improvement. In these terms, Amdahl's Law states that:

![image](https://github.com/user-attachments/assets/a23a4965-15e5-49b2-95f1-2c36b3c02e2e)

However, more insight can be gained from the relative form shown below.

![image](https://github.com/user-attachments/assets/65b0c552-241c-40a0-accb-c8e956b6f704)

In this form it is easier to see what happens to the limit as `S` increases, where `S_overall` reaches a maximum of `1 / 1-f`.”

Despite advantages like improved performance and reduced power consumption, multicore processors face challenges such as heat and power issues, with increased transistor density contributing to higher power consumption. Effective power management, including turning off inactive cores and operating at lower frequencies, is crucial. Success in multicore technology depends on well-designed algorithms that utilize all cores efficiently; inefficient algorithms can lead to core starvation and undermine multicore benefits.

In conclusion, although multicore processors face challenges, their advantages—such as improved performance, lower power consumption, and enhanced parallel processing capabilities—generally outweigh the drawbacks. Proper software design is essential to fully harness multicore technology's potential.


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

Basic, non parallel processing works by having a queue of instructions lined up to then be executed one by one.
Each completed instruction then makes its way over to its destination.

![image](https://github.com/user-attachments/assets/f2804a68-11f7-41ef-8134-3589b47f283e)

The main limitation with this approach is the processor's max speed.
The CPU can only work so fast, due to a multitude of reasons, the main one however being due to heat
(speeding up the CPU any more could cause it to literally melt).

Parallel processing works by dividing the intructions into multiple smaller queues by utilizing multiple processors.
This method reduces the overall workload that a single processor needs to complete.
This however leads to a completely new set of drawbacks, mainly bugs.
These bugs arise due to dependency issues, where one task in say processor 1 gets finished faster than a task it depends on, that has yet to be completed in processor 2.
These bugs can include latency, lag, and incorrect/inaccurate information, among other issues.
A potential fix briefly mentioned in the video is to chain all dependant tasks through the same processor (as shown in the image with the green and orange tasks) to assure they all get done in order.

![image](https://github.com/user-attachments/assets/3f8aa53b-562d-407c-b6ba-e2de5c1b0da7)


### 3. https://www.youtube.com/watch?v=IZfWjg3U3mA

Multi Processing Operating refers to using 2 or more CPUs within one computer, all sharing the same core components such as the Bus and RAM.
Simply put, having 2 processors working simultaneously on completing a queue of 4 tasks is 2x faster than one processor working on those same 4 tasks.

2 types of Multi Processing Operating Systems:
Symmetric Multiprocessing
Asymmetric Multiprocessing

Symmetric Multiprocessing:
Every CPU is connected together in an "equal" manner, where each one of them is allowed to work on any command at any time.
Each CPU also has access to all other components such as ROM, RAM, peripherals, etc.
One OS controls all the CPUs

![image](https://github.com/user-attachments/assets/3f0075de-8d7c-4f51-ba8f-ab02c77395ca)

This method causes some issues due to all CPUs accessing different hardware all at the same time, which causes a rather confusing connection network, increasing circuit production costs.

Asymmetric Multiprocessing:
CPU Hierarchy System
One processor will act as a "leader", assigning tasks to all other processors under it.
This leading CPU is in charge of communicating with all other hardware (input/output, RAM, peripherals, etc.)
Secondary processors are only used to increase the processing speed of the main one by completing instructions in its stead.

![image](https://github.com/user-attachments/assets/4d3d5e8d-a723-463a-aff8-b5f80b00e189)

Advantages of Multiprocessing:
1. Increased Throughput
   - More work is able to get done in a shorter amount of time thanks to the ability to work on multiple tasks simultaneously.
2. Increased Reliability
   - In case of a processor malfunction or failure, the other processors will still keep running (as opposed to a single processor system, where the entire     system fails as soon as the only CPU gets damaged).
3. Cost Saving
   - As opposed to having 4 separate single processor computors, we get the same amount of CPU power condensed into only 1 computor, saving money on hardware like RAM, monitors, and peripheral devices.
4. Parallel Processing
   - Since processors can only work on 1 process at a time, having multiple processors will allow us to work on mutiple instructions at once.


### 4. https://web.archive.org/web/20111125035151/http://www.csa.com/discoveryguides/multicore/review.pdf

A paragraph summarizing the history of microprocessors, posted under screenshot format due to the information density in the text.

![image](https://github.com/user-attachments/assets/03cadb01-192e-440a-b56f-915b9fef14c3)

(Gordon) Moore's Law:
The number of transistors in a processor will double each year (said in 1965)
The number of transistors in a processor will double each 2 years (revised in 1975)
Computer performance will double each 1.5 years (revised by David House)

![image](https://github.com/user-attachments/assets/6e6c8bfa-439f-4bd2-b3c9-8824560c7813)

David House's prediction needed to be tweaked, as processor frequency reached a plateau (image below is a response from an AI, while unverified, the response still prooves the point that processing frequency has not increased in a while).

![image](https://github.com/user-attachments/assets/d5f843e8-cb4c-4c97-ba4d-9736846ea53d)

Multi-core processors usually run at a lower frequency than single-core ones, reducing the stress on each core while maintaing efficiency.

"By incorporating multiple cores, each core is able to run at a lower frequency, dividing power among them normally given to a single core. The result is a big performance increase over a single core processor. It can be observed that increasing clock frequency by 20% to a single core delivers a 13% performance gain, but requires 73% greater power. Conversely, decreasing clock frequency by 20% reduces power usage by 49%, but causes only 13% performance loss [2]. If a second core is added into the single core architecture, it results in a dual-core processor that at 20% reduced clock frequency; it can effectively deliver 73% more performance while using approximately the same power as a single-core processor at maximum frequency."

Above quote/statistics taken from:
**https://www.researchgate.net/figure/Performance-comparison-between-a-single-core-and-multi-core-processor_fig1_224105796#:~:text=By%20incorporating%20multiple%20cores%2C%20each%20core%20is%20able,13%25%20performance%20gain%2C%20but%20requires%2073%25%20greater%20power.**

Intel's Pentium 4 had frequencies from 1.3 to 3.8GHz over its 8 year lifetime. Chip size decreased, transistor count increased, heat dissipation reached dangerous levels.

Boosting single-core processor performance:
Superscalar process that can issue multiple instructions at the same time. Pre-fetches instructions, breaks them down into sub-components, and executes them out of order.
To overcome branch instructions, the processor needs to gather all necessary information. To save time, it will try to predict which path will be taken. If it's wrong, it throws out all incorrect data and restarts with the correct path (time loss isn't significant). Loop unrolling and neural network based predictors are also used to reduce incorrect predictions.

"Other techniques used for performance enhancement include register renaming, trace caches, reorder buffers, dynamic/software scheduling, and data value prediction." (Included here just for info, will most likely not be used).


### 5. https://ijret.org/volumes/2015v04/i09/IJRET20150409015.pdf

This study largely focuses on the technology of multicore processor technology itself, as well as real-world use case issues regarding power, temperature and interconnectivity issues and the addition of more cores.

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

