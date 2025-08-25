# ICIA_NeuroABench

## 📝 Overview
Our paper introduces **NeuroABench**, a new multimodal benchmark for evaluating anatomical understanding in neurosurgical videos, and finds that while state-of-the-art multimodal large language models show promise, they still fall short of human-level performance in anatomical identification tasks.  

<figure>
  <img src="IMAGE/dataset_example.jpg" alt="The reward and S(q) curves of the Qwen-2.5-VL-7B during training on the SGG-VQA dataset." width="1000"/>
  <figcaption><b>Figure 1:</b> Examples of NeuroABench. This benchmark is constructed using neurosurgical anatomical content derived from publicly available educational videos.</figcaption>
</figure>


<figure>
  <img src="IMAGE/Figure1.jpg" alt="The reward and S(q) curves of the Qwen-2.5-VL-7B during training on the SGG-VQA dataset." width="1000"/>
  <figcaption><b>Figure 2:</b> <b>Pipeline illustration of NeuroABench.</b> The data collection can be divided into three main steps: 1) We search hundreds of videos and teaching
manuals from the Neurosurgical Atlas, then keep 89 high-quality videos and 32 teaching manuals after filtering. 2) We use Gemini-1.5-Pro to annotate videos
with the instructions of clinician-reviewed structured progress extracted from teaching manuals. 3) The annotated images go through additional validation and
experts’ selection. From these images, we generate question-and-answer pairs for each landmark anatomy featured in the videos.</figcaption>
</figure>

## 📚 Dataset

The benchmark text data used in this project is provided in the xxx.json file.

Please note: Benchmark images are not included in this repository.
The benchmark images can be downloaded from [this link](https://example.com/download-link).

## ✍ Testing Results 

| Model                  | Params | Instance Acc | Instance Precision | Instance Recall | Instance F1 | Anatomy Precision | Anatomy Recall | Anatomy F1 |
|------------------------|--------|--------------|-------------------|----------------|-------------|-------------------|---------------|------------|
| Random                 | -      | 19.48        | 19.99             | 20.01          | 19.96       | 16.86             | 12.10         | 1.68       |
|                        |        |              |                   |                |             |                   |               |            |
| **Open-Source MLLMs**  |        |              |                   |                |             |                   |               |            |
| mPLUG-Owl3 [17]        | 8B     | 25.76        | 20.37             | 25.36          | 22.55       | 19.53             | 17.96         | 15.80      |
| Deepseek-VL2* [18]     | 4.5B   | 22.54        | 16.06             | 23.35          | 16.93       | 17.53             | 14.96         | 14.65      |
| LLaVA-NeXT [19]        | 7B     | 28.82        | 24.06             | 28.90          | 25.67       | 23.75             | 18.82         | 18.64      |
| Baichuan-Omni-1.5 [20] | 7B     | 27.25        | 27.90             | 27.22          | 27.29       | 20.45             | 15.07         | 15.10      |
| Qwen2.5-VL [21]        | 7B     | 31.21        | 33.69             | 32.18          | 32.15       | 21.00             | 19.04         | 18.01      |
| LLaVA-NeXT [19]        | 72B    | 27.53        | 26.70             | 27.43          | 25.45       | 16.72             | 16.62         | 14.60      |
| Qwen2.5-VL [21]        | 72B    | 37.44        | 40.57             | 37.27          | 37.52       | 25.91             | 20.20         | 20.17      |
|                        |        |              |                   |                |             |                   |               |            |
| **Proprietary MLLMs**  |        |              |                   |                |             |                   |               |            |
| GPT-4o [22]            | -      | 30.21        | 38.19             | 29.59          | 29.93       | 25.11             | 20.48         | 19.56      |
| Gemini-1.5-Pro         | -      | 38.83        | 41.93             | 39.82          | 35.88       | 22.54             | 23.35         | 20.57      |
| Gemini-2.0-Flash [23]  | -      | 40.87        | 46.61             | 41.07          | 38.56       | **29.68**         | **27.02**     | **25.52**  |
| Qwen-VL-MAX [24]       | -      | 16.46        | 18.26             | 18.31          | 12.13       | 11.52             | 9.29          | 9.29       |
| Claude-3.5-Sonnet [25] | -      | 41.51        | 42.52             | 41.34          | 38.14       | **29.44**         | **27.03**     | **24.52**  |
| Claude-3.7-Sonnet [26] | -      | 33.27        | 37.63             | 33.11          | 30.98       | 25.29             | 20.00         | 20.35      |
|                        |        |              |                   |                |             |                   |               |            |
| **Medical Special Models** |    |              |                   |                |             |                   |               |            |
| LLaVA-Med-v1.5 [27]    | 7B     | 15.01        | 12.54             | 15.09          | 7.66        | 13.89             | 10.53         | 10.79      |
| HuatuoGPT-Vision       | 7B     | 30.31        | 34.40             | 30.87          | 28.31       | 22.26             | 20.98         | 18.85      |
| HuatuoGPT-Vision [28]  | 34B    | 35.48        | 36.52             | 36.40          | 32.71       | 24.17             | 23.76         | 21.49      |
