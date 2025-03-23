# Video analysis using Amazon Bedrock for road safety
## Document Purpose
This project outlines our approaches and experimentation to building a comprehensive road safety analysis system using multi-camera video feeds. Our goal is to provide actionable insights and recommendations to enhance driver safety through advanced video processing and AI techniques.

## Abstract
The Road Safety Video anaylsis will processes multiple camera feeds to analyze driving patterns, identify potential hazards, and generate safety recommendations. By leveraging different LLM in Bedrock, we aim to reduce accidents and improve overall road safety.This can be additionally used to coach and train the fleet drivers. 


## Proposed Solution
We are developing an integrated system that utilizes multiple video processing approaches to maximize accuracy and efficiency.  We will be leveraging Amazon Bedrock for the experimentation. Our solution incorporates:

1. Nova Pro video processing pipeline for detailed frame-by-frame analysis
2. Claude-based image grid processing for comprehensive scene understanding
3. Hybrid summarization using both Nova and Sonnet models

**Note:** At the time of writing this blog, Anthropic Claude models provides support for image(not video), however Nova pro provides support for videos as well. 


## Technical Approach

### Video Processing Options

For stitching the videos together, you can leverage the following notebook:
[Combine_video.ipynb](Combine_videos.ipynb)



| Experiment # | Details | Comments | Link |
|--------|----------|-----------|------|
| **1A** | Video - individual videos <br>Then summarize with nova | Multiple calls | [Notebook 1](experiments/notebook1.ipynb#1A) |
| **1B** | Video - stitched video | 1 call <br>Stitched video is done using python code and might have resolution/quality issue | [Notebook 1](experiments/notebook1.ipynb#1B) |
| **1C** | Video - individual videos <br>Then summarize with sonnet | Multiple calls | [Notebook 1](experiments/notebook1.ipynb#1C) |
| **2A** | Video - stitched video | 1 call <br>Stitched video is done using python code and might have resolution/quality issue | [Notebook 2](experiments/notebook2.ipynb#2A) |
| **2B** | Video image grid - individual grid <br>Then summarize with sonnet | Multiple calls | [Notebook 2](experiments/notebook2.ipynb#2B) |


This experimental setup explores different approaches to video analysis using two main methods: direct video processing and video image grid analysis. The experiments are divided into two notebooks focusing on different methodologies:

### Notebook 1: Video Analysis with Nova Pro (Experiments 1A-1C)
Experiments 1A through 1C investigate different approaches using Nova Pro:
- **1A** processes individual videos separately and then combines the summaries, allowing for detailed analysis of each video but requiring multiple API calls.
- **1B** tests a single-call approach using a stitched video, which is more efficient but may face quality trade-offs due to the video combination process.
- **1C** follows the individual video approach like 1A but uses Sonnet for summarization, providing a comparison between different summarization methods.

### Notebook 2: Video Image Grid Analysis with Claude (Experiments 2A-2B)
Experiments 2A and 2B explore alternative approaches using image grid analysis:
- **2A** uses a stitched video similar to 1B but processes it through Claude, offering a different perspective on combined video analysis.
- **2B** processes individual image grids and uses Sonnet for summarization, potentially providing more detailed analysis while requiring multiple processing steps.

Please note - these are just experiment and you can change the prompt, frames sampling per your usecase. 

## Contributing
Refer to [details](CONTRIBUTING.md)

## Authors and acknowledgment
Neelam Koshiya

## License
This project is licensed under the MIT License


