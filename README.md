# Summary Extraction and Relevance Identification from Spotify Podcasts

## Description
This repository contains the code and reports used in CS410 Fa21 course project. This document describes the usage of all scripts and functions defined in them. For more information about the project tasks, please see the the [proposal](CS_410_TIS_Project_proposal.pdf) and [progress-report](CS_410_TIS_Project_Progress_Report.pdf).

## File Descriptions
| File Name | Task Summary |
| ----------- | ----------- |
| [`extract_data.py`](extract_data.py) | Extract episode transcripts and creator descriptions from the raw dataset. Process them combined CSVs using episode prefix as unique id|
| [`content_selection.py`](content_selection.py) | Reduces episode transcripts to the top 5 most important sentences according to TextRank algorithm |

Each of the above files are accompanied by a corresponding `ipynb` notebook file as well. CAs/TAs are requested to use those notebooks for evaluation. They can be imported into a local jupyter instance or Google Colab

## Function Descriptions:

### `extract_episode_lists_and_transcripts`
Source: [`extract_data.py`](extract_data.py)
Inputs: `data_id` (int) Each of the raw data gzip files decompress into `spotify-podcasts-2020/podcasts-transcripts/<data_id>`.
Output: tuple of two dicts - `show_episodes_dict` (Schema: `{show_prefix : [episode_prefix]}`) and `episode_transcript_dict` (Schema: `{episode_prefix: transcript_text}`)

### `generate_summ_dataset`
Source: [`extract_data.py`](extract_data.py)
Inputs: None
Outputs: Reads the dictionaries generated by `extract_episode_lists_and_transcripts` and writes a merged CSV file with the columns `(ep_prefix, ep_transcript, ep_description)`

### <another-function-X-in-content-selection.py>
Input: None
Outputs: Loads the merged CSV generated by `generate_summ_dataset` into a Pandas dataframe. Adds a new `n_sentences` (number of sentences in transcript) column.

### `text_rank_selection`
Source: [`content_selection.py`](content_selection.py)
Inputs: `transcript` (`str`), `n` (`int`)
Outputs:  Uses `summa` library to get the top 5 sentences from episode transcript text. Uses `n` to determine the percentage of sentences to feed into the `ratio` param in `summa.summarizer(ratio=)`

## Usage

### Install dependencies
`pip install -r requirements.txt`

### Run data extraction
Load `extract_data.ipynb` into `jupyter` or Google Colab. Execute all cells.

### Perform content selection using TextRank
Load `content_selection.ipynb` into `jupyter` or Google Colab. Execute all cells.

### Step 4
Inference via T5 Transformer model.

### Step 5

