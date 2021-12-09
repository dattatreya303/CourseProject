# Summary Extraction and Relevance Identification from Spotify Podcasts

## Description
This repository contains the code and reports used in CS410 Fa21 course project. This document describes the usage of all scripts and functions defined in them. For more information about the project tasks, please see the the [proposal](CS_410_TIS_Project_proposal.pdf) and [progress-report](CS_410_TIS_Project_Progress_Report.pdf).

## File Descriptions
| File Name | Task Summary |
| ----------- | ----------- |
| [extract-data.py](extract-data.py) | Extract episode transcripts and creator descriptions from the raw dataset. Process them combined csvs using episode prefix as unique id|
| [content-selection.py](content-selection.py) | Reduces episode transcripts to the top 5 most important sentences according to TextRank algorithm |

Each of the above files are accompanied by a corresponding `ipynb` notebook file as well. CAs/TAs are requested to use those notebooks for evaluation. They can be imported into a local jupyter instance or Google Colab

## Function Descriptions:

### `extract_episode_lists_and_transcripts`
Source: [extract-data.py](extract-data.py)
Inputs:
Output: