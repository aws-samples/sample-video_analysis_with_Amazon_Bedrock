# Video analysis using Amazon Bedrock for road safety
## Document Purpose
This project outlines our approaches and experimentation to building a comprehensive road safety analysis system using multi-camera video feeds. Our goal is to provide actionable insights and recommendations to enhance driver safety through advanced video processing and AI techniques.

## Abstract
The Road Safety Video anaylsis will processes multiple camera feeds to analyze driving patterns, identify potential hazards, and generate safety recommendations. By leveraging different LLM in Bedrock, we aim to reduce accidents and improve overall road safety.This can be additionally used to coach and train the fleet drivers. 

## Problem Statement
Current road safety systems often rely on reactive measures or limited data points. There is a critical need for:
- Real-time analysis of driving conditions and behaviors
- Comprehensive multi-angle video processing
- Actionable safety recommendations for drivers
- Scalable processing of large video datasets

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

    


## Success Metrics
- Processing accuracy for different lighting conditions
- System latency and real-time performance
- Quality of safety recommendations
- Scalability with multiple camera feeds


## Contributing
Refer to [details](CONTRIBUTING.md)

## Authors and acknowledgment
Neelam Koshiya

## License
This project is licensed under the MIT License


