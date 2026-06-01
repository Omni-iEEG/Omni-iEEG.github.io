---
layout: research
permalink: /omni-ieeg/
title: "Omni-iEEG: A Large-Scale, Comprehensive iEEG Dataset and Benchmark for Epilepsy Research"
page_title: "Omni-iEEG: A Large-Scale, Comprehensive iEEG Dataset and Benchmark for Epilepsy Research"
redirect_from:
  - /omni-ieeg
description: "<h3 style='color:red'>ICLR 2026</h3>"
authors:
  - {name: "Chenda Duan<sup>*</sup>", url: "https://chendaduan.com/"}
  - {name: "Yipeng Zhang<sup>*</sup>", url: "https://scholar.google.com/citations?user=VESaC8wAAAAJ&hl=en"}
  - {name: "Sotaro Kanai", url: "https://nariailab.dgsom.ucla.edu/people/sotaro-kanai-md-phd"}
  - {name: "Yuanyi Ding", url: "https://www.linkedin.com/in/yuanyi-ding-4a981a132/"}
  - {name: "Atsuro Daida", url: "https://scholar.google.com/citations?user=HN3W_xwAAAAJ&hl=en"}
  - {name: "Pengyue Yu", url: "#"}
  - {name: "Tiancheng Zheng", url: "#"}
  - {name: "Naoto Kuroda", url: "#"}
  - {name: "Shaun A. Hussain", url: "#"}
  - {name: "Eishi Asano", url: "#"}
  - {name: "Hiroki Nariai", url: "https://www.uclahealth.org/providers/hiroki-nariai"}
  - {name: "Vwani Roychowdhury", url: "https://www.vwaniroychowdhury.com/"}
institutions:
  - {name: "UCLA Samueli School of Engineering"}
  - {name: "UCLA Mattel Children’s Hospital, David Geffen School of Medicine"}
  - {name: "Children’s Hospital of Michigan, Wayne State University School of Medicine"}
  - {name: "<sup>*</sup> Equal Contribution"}
nav: false
nav_order: 1
dataset_link: https://huggingface.co/datasets/Omni-iEEG/Omni-iEEG
code_link: https://github.com/Omni-iEEG/Omni-iEEG
leaderboard_link: /leaderboard/
pdf_link:  https://openreview.net/forum?id=rv9lQpY5cG # omit if you don't have one yet
---


<style>
.video-container {
  position: relative;
  max-width: 100%; /* Adjust this value to control the maximum width of the video container */
   margin: 0 auto 0; /* Optional: center the video container horizontally */
}

.teaser {
  margin: 0 auto; /* Optional: center the video container horizontally */
}

.video-container video {
  display: block;
  margin: 0 auto;
  max-width: 100%;
  max-height: 100%;
}


.video-grid {
    margin-top: 18px;
    display: grid;
    grid-template-rows: 1fr 1fr 1fr; /* Two rows */
    grid-gap: 70px; /* Space between items */
    justify-items: center; /* Horizontally center items */
    align-items: center; /* Vertically center items */
}

.video-grid figure {
    display: flex;
    flex-direction: column; /* Stack video and caption */
    align-items: center; /* Center video and caption */
    justify-content: center; /* Center content */
    margin: 0; /* Reset default margin */
}

.video-grid video {
    display: block;
    width: 80%; /* Adjust as needed */
    height: auto; /* Maintain aspect ratio */
}

.video-section {
  margin-bottom: 60px;
}

video {
  width: 100%;
  /* max-width: 1000px; */
  height: auto;
  margin: 0 auto;
}

.dots {
  display: flex;
  justify-content: center;
  gap: 10px;
}

.dot {
  font-size: 24px;
  cursor: pointer;
  color: #aaa;
}

.dot.active {
  color: #333;
}

/* Make teaser image full width with flexible height */
.img-container {
  width: 100%;
  margin: 0 auto;
}

.img-container img {
  display: block;
  width: 100%;
  height: auto;
}

/* Ensure figures stay within content boxes */
.research-section img,
.research-section .white-background img {
  max-width: 100%;
  height: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.white-background {
  background: #fff;
  padding: 12px;
  border-radius: 8px;
}

.announcement-banner {
  color: red;
  text-align: center;
  font-size: 1.5em;
  font-weight: bold;
}
</style>

<div class="img-container" style="margin: auto;">
  <img src="{{ '/assets/img/omniieeg/omniieeg.png' | relative_url }}" alt="Omni-iEEG teaser">
</div>



<div class="research-section">
  <ul style="list-style-type: none; padding-left: 0;">
    <strong>TL;DR: </strong> 
    Omni-iEEG is the first <strong>large-scale, harmonized intracranial EEG dataset</strong>, 
    comprising <strong>302 patients, 178 hours of recordings, and 36K expert annotations</strong>. 
    It establishes <strong>clinically meaningful and unified benchmarks</strong> with standardized evaluation 
    metrics to bridge <strong>clinical neuroscience</strong> and <strong>machine learning</strong>.
  </ul>
</div>

<div class="research-section">
  <h3 style="text-align: center">Dataset Overview</h3>
  <div class="white-background">
    <img src="../assets/img/omniieeg/table1_dataset.png">
  </div>
  <p>
    Omni-iEEG integrates recordings from eight epilepsy centers with harmonized clinical metadata 
    (SOZ, resection regions, surgical outcomes, anatomical labels). Data will be released in 
    <strong>BIDS format</strong> with an accompanying utility library on Github. We will also released the data in hugginface for easier access.
  </p>
</div>

<div class="research-section">
  <h3 style="text-align: center">Event Annotation</h3>
  <div class="white-background">
    <img src="../assets/img/omniieeg/table2_event.png">
  </div>
  <p>
    Over <strong>36,000 high-frequency oscillation (HFO) events</strong> were annotated, combining 
    new and previously published events. Candidate events were detected with three established 
    algorithms (STE, MNI, Hilbert) and reviewed by <strong>four board-certified epileptologists</strong>. 
    Each event was labeled as <em>artifact</em>, <em>non-spkHFO</em>, or <em>spkHFO</em>.
  </p>
  <p>
    To ensure quality, annotators first calibrated on a shared set, then labeled independently. 
    Inter-rater agreement was high (<strong>Fleiss’ κ = 0.93</strong>), reflecting strong consistency 
    and clinical reliability. All signals were resampled to 1 kHz and standardized with bipolar montage 
    where appropriate.
  </p>
</div>

<div class="research-section">
  <h3 style="text-align: center">Benchmark Tasks</h3>
  <p>
    <strong>Task 1:</strong> Clinical prior-driven pathological event classification (spkHFO vs non-spkHFO vs artifact).<br>
    <strong>Task 2:</strong> Pathological brain region identification (SOZ vs normal channels, outcome prediction).<br>
    <strong>Exploratory Tasks:</strong> Anatomical location classification, Ictal period identification, Sleep–Awake classification.
  </p>
</div>

<div class="research-section">
  <h3 style="text-align: center">Task 1:Pathological Event Classification</h3>
  <div class="white-background">
    <img src="../assets/img/omniieeg/table4_result.png">
  </div>
  <p>
    We benchmark recent competitive baseline event classification methods. PyHFO method trained on Omni-iEEG achieves the highest F1 (~0.81), 
    demonstrating strong performance on spkHFO detection.
  </p>
</div>

<div class="research-section">
  <h3 style="text-align: center">Pathological Brain Region Identification</h3>
  <div class="white-background">
    <img src="../assets/img/omniieeg/table5_result.png">
  </div>
  <p>
    Both event-based and segment-based models are evaluated. Segment models (TimeConv-CNN, CLAP, SEEG-Net) 
    achieve up to <strong>0.81 AUC</strong> in pathological channel identification and correlate well with 
    surgical outcome prediction.
  </p>
</div>
<div class="research-section">
  <h3 style="text-align: center">Exploratory Tasks</h3>
  <div class="white-background">
    <img src="../assets/img/omniieeg/table6_supp.png">
  </div>
  <p>
    Three exploratory tasks extend Omni-iEEG:
  </p>
  <ul>
    <li><strong>Anatomical Location Identification:</strong> 5-class lobes and 12-class subregions.</li>
    <li><strong>Ictal Period Classification:</strong> detect ictal vs interictal periods.</li>
    <li><strong>Sleep–Awake Classification:</strong> identify vigilance states in invasive recordings.</li>
  </ul>
  <p>
    Pretrained audio models (<strong>CLAP</strong>) perform strongly (e.g., 
    <em>F1 = 0.92, Acc = 0.93</em> on ictal classification), while CNNs remain competitive.
  </p>
</div>
<div class="research-section">
  <h3 style="text-align: center">Conclusion</h3>
  <p>
    Omni-iEEG provides a unified, clinically validated foundation for data-driven epilepsy research. 
    It enables systematic benchmarking, improves reproducibility, and opens new research directions 
    at the intersection of <strong>clinical neurophysiology</strong> and <strong>AI</strong>.
  </p>
</div>

<div class="research-section">
  <h3 style="text-align: center">Reference</h3>
<pre><code>@inproceedings{duan2026omniieeg,
  title={Omni-iEEG: A Large-Scale, Comprehensive iEEG Dataset and Benchmark for Epilepsy Research},
  author={Duan, Chenda and Zhang, Yipeng and Kanai, Sotaro and Ding, Yuanyi and Daida, Atsuro and Yu, Pengyue and Zheng, Tiancheng and Kuroda, Naoto and Hussain, Shaun A. and Asano, Eishi and Nariai, Hiroki and Roychowdhury, Vwani},
  booktitle = {International Conference on Learning Representations (ICLR)},
  year      = {2026}
}
</code></pre>
</div>
