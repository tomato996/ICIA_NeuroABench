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

## ❓ Testing Model 

