# Case-Study: Parallel Processing and Multicore Processors

- by Hariharan Chithra 100812562 & Karlo Khoury-Hillman (100816230) 

## Introduction

Multicore processors are a parallel computing architecture which consists of at least two or more cores that read and write CPU instructions on a single chip. 

The main feature of these processors is their ability to run multiple instructions at the same time, which can decrease the amount of time needed to execute programs when compared to single-core processors, which run instructions one at a time. While single-core processors can have higher core performance, applications optimized for parallel processing will have an overall faster result. 

This approach, however, is theorized to have diminishing returns. According to Moore’s Law, the number of cores on a chip would double once every 18 months when looking at the general progression of this technology(successive silicone generations), however, it is largely believed that while it is extremely beneficial when comparing the differences between each of the earlier generations, such as dual and quad-core, diminishing returns are expected around 8 and 16 more cores.

The goal of this paper is to take a look into multi-core processor technology, understand its impact and evolution, and identify the practical need and application for this technology, as well as its advantages and limitations.


## Literature Review

The studies on parallel hardware and software investigates evolutionary approaches, highlighting their effectiveness for systems with 2-8 cores but noting potential diminishing returns when scaling to 16 or 32 cores. 

This is in line with instruction-level parallelism and reflects the industry's trend of doubling cores per silicon generation. Key areas of focus include ease of programming for parallel systems, efficiency metrics (measured in Million Instructions per Second or MIPS, per Watt, per area of silicon, and per development dollar), and strategies to enhance programmer productivity through human-centric design. It also underscores the importance of testing and orchestrating functionality via libraries and virtual machines for optimal system performance.

In multi-processing operating systems, two or more CPUs within a single computer share core components like the bus and RAM, enabling simultaneous task execution. This arrangement effectively doubles processing speed compared to a single-processor system. 

![image](https://github.com/user-attachments/assets/59169b8a-a668-4642-ad68-a338d99e2b21)

Multi-processing systems are categorized into:

- Symmetric Multiprocessing (SMP): All CPUs are equally connected, allowing any CPU to handle any command and access all system components, including ROM, RAM, and peripherals. A single operating system manages all CPUs, but this can lead to complex connection networks and increased production costs due to simultaneous hardware access by multiple CPUs.

![image](https://github.com/user-attachments/assets/3f0075de-8d7c-4f51-ba8f-ab02c77395ca)
  
- Asymmetric Multiprocessing (AMP): AMP features a hierarchical structure where one "leader" CPU assigns tasks to subordinate processors and manages communication with hardware. Secondary processors enhance overall processing speed by executing tasks on behalf of the primary CPU.

![image](https://github.com/user-attachments/assets/4d3d5e8d-a723-463a-aff8-b5f80b00e189)


The advantages of multi-processing include increased throughput through simultaneous task handling, enhanced system reliability (since other processors continue to function if one fails), cost savings by consolidating CPU power into a single system, and improved parallel processing capabilities.

The history of microprocessors is significantly influenced by Moore's Law, proposed in 1965, which initially predicted that the number of transistors on a processor would double each year. This was revised in 1975 to a doubling every two years, with David House later estimating performance doubling every 1.5 years. However, as processor frequencies reached a plateau, these predictions required adjustment.

![image](https://github.com/user-attachments/assets/6e6c8bfa-439f-4bd2-b3c9-8824560c7813)


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

Multicore processors have distinct advantages and disadvantages when compared to single-core processors.
### Advantages:

The main advantages of multi-core processors are as follows:

Improved performance:

Combining several cores on a single die improves performance related to the cache snoop, i.e, data stored in the cache is processed more efficiently when compared to the single-core approach, allowing for it to be cleared for further processes.
It also allows for the processor to work at a higher overall clock rate. At the same clock frequency, the multicore processor will process more data than the single-core processor

Energy efficiency:

Multicore processors deliver high performance and carry out tasks at a comparatively lower energy rate when compared with a single core processor, which is crucial factor in appliances such as mobile phones which operate on batteries. Also, since the cores are fabricated close to each other on the same chip, the signals between them travel at shorter distances due to which there is less attenuation of signals. Since the signals don’t attenuate much, more data is transferred in a set period without concerns for repetition of data

### Limitations and Challenges:

Despite its advantages, multicore technology faces its own challenges, which are as follows

Power and temperature

While multicore processors use less energy on a per core basis, any unused cores will still consume power. Additionally, multicore processors generate much more heat than single-core processors, which can lead to thermal throttling(The CPU either having parameters to reduce clock speeds to reduce heat and prevent damage, or reduced performance due to heat damage). This can be somewhat mitigated by turning off unused cores

Optimization:

Programmers would need to keep in mind optimizations to take advantage of multi-core processing and would have to spend time optimizing their program to run efficiently on a multicore, as starvation can occur with cores being idle and only one being used to run the program.

Memory and bus handling:

Memory requests to the bus and DRAM would have to be handled to enhance speed and ensure communication between cores. Issues can also occur when multiple cores and reading and writing to the same bus, and there is also a chance of denial of memory to occur as other cores use up memory resources

### Advancements:

The field of multicore processors and parallel processing have had many transformative developments, leading to several improvements and breakthroughs for the technology, some of which are highlighted as follows:

Improved core performance:

Despite plateaus in the efficient addition of further cores, several advancements have been made regarding clock speeds and multithreading. Newer multicore CPU architectures have had a greater focus on improving individual core performance and clock speeds, with major increases in every successive generation.

Cache:

Additional advancements have been made over the years in the efficient use of L3 cache through improvements in cache protocols, greatly improving performance.

Development of new architectures:

The focus on multicore processors has given rise to more efficient multicore architectures such as AMD Ryzen and Intel Xeon which are well known for their multithreading capabilities, significantly increasing parallel processing power and enabling more efficient execution of complex tasks.
Additionally, these architectures have led to the development of programming models like CUDA for GPU programming, which has simplified the development of parallel applications

Improvement in power management:

The advancement of techniques such as Dynamic Voltage and Frequency Scaling (DVFS) and power gating have increased efficiency in power consumption in multicore processors

## Application:

### Mobile Devices

Multicore processors in smartphones and tablets allow for seamless multitasking and efficient handling of complex applications. This architecture enhances performance and responsiveness, enabling users to run multiple apps simultaneously, such as streaming videos while browsing the web or using social media, without noticeable lag or decreased battery life. This efficiency is crucial for maintaining a smooth user experience and extending battery life.

###Artificial Intelligence

AI applications leverage multicore processors to accelerate machine learning model training and inference tasks. Parallel processing allows for the simultaneous handling of vast datasets and complex algorithms, significantly reducing training times for deep learning models and enabling real-time decision-making in applications such as autonomous vehicles, natural language processing, etc.

### Entertainment and Media

In the entertainment industry, multicore processors enhance video rendering, gaming experiences, and content creation. By distributing processing tasks across multiple cores, applications such as video editing software and high-definition games achieve smoother performance, higher quality graphics, and faster processing times, resulting in a better overall user experience.

## Conclusion:

## References:

Alkhanafseh, M., Sarhan, S., Surakhi, O. M. (2018). A Survey on Parallel Multicore Computing: Performance & Improvement. www.researchgate.net. (PDF) A Survey on   Parallel Multicore Computing: Performance & Improvement (researchgate.net)

Asanovic, K., Bodik, R., Christopher, B., Joseph, C., Gebis, J., Husbands, P., Keutzer, K., Patterson, D., Lester, W., John, P., Samuel, S., Williams, W., & Yelick, K. (2006). The Landscape of Parallel Computing Research: A View from Berkeley. https://www2.eecs.berkeley.edu/Pubs/TechRpts/2006/EECS-2006-183.pdf

Chowdhury, M., Roy, A., Xu, J. (2009) Multi-core processors: A new way forward and challenges. www.researchgate.net. (PDF) Multi-core processors: A new way forward and challenges (researchgate.net)

Klein, J. F. (2011) Amdahl’s Law - Wolfram Demonstrations Project. Demonstrations.wolfram.com. https://demonstrations.wolfram.com/AmdahlsLaw/

Mardox, H. (2014). Parallel Computing Explained In 3 Minutes. Www.youtube.com. https://www.youtube.com/watch?v=q7sgzDH1cR8

making IT simple. (2020). Multiprocessing Operating System | Easy Explanation | Using Animation. Www.youtube.com. https://www.youtube.com/watch?v=IZfWjg3U3mA

Schauer, B. (2008). Multicore Processors – A Necessity. Web.archive.org. https://web.archive.org/web/20111125035151/http://www.csa.com/discoveryguides/multicore/review.pdf

‌Sethi, A., Kushwah, H. (2015). MULTICORE PROCESSOR TECHNOLOGY-ADVANTAGES AND CHALLENGES. In IJRET: International Journal of Research in Engineering and Technology (pp. 2321–7308). https://ijret.org/volumes/2015v04/i09/IJRET20150409015.pdf
