# Dataset README

## Overview
This dataset contains the experimental data used in *A Survey of Methods for Estimating Hurst Exponent of Time Sequence* (https://arxiv.org/abs/2310.19051). The dataset includes multiple CSV files and a NumPy format file (.npy), which store various data collected during the experiments. This README file provides a detailed description of each file and its contents.

## File Structure

data/
├── FGN_*_30.csv
├── Random_*_30.csv
├── rsif20210272_si_002.csv
├── RT-HS-P1.npy
└── README.md

## File Descriptions

### FGN_*_30.csv

- **Description**: Multiple sets of FGN sequences with Hurst exponent values between 0.3 and 0.8. The asterisk (*) represents the Hurst exponent value of the FGN sequence, and 30 represents the number of experiments.
- **Columns**:
  - `f{i}`: The FGN sequence used in i-th experiment, with a sequence length of 30,000.

### Random_*_30.csv

- **Description**: Multiple sets of FGN sequences with differnent random distributions. The asterisk (*) represents six types random distributions, including normal distribution N(0, 1), Chi-square distribution X^2(1), geometric distribution GE(0.25), Poisson distribution P(5), exponential distribution Exp(1), and uniform distribution U(0, 1). And 30 represents the number of experiments.
- **Columns**:
  - `X{i}`: The FGN sequence used in i-th experiment, with a sequence length of 10,000.

### rsif20210272_si_002.csv
- **Description**: The reaction time (RT) data from 20 participants in both test groups were collected and made publicly accessible for retrieval (https://royalsocietypublishing.org/doi/suppl/10.1098/rsif.2021.
0272).
- **Columns**:
  - `condition`: experimental condition: HS (Human Speech) or TSS (text-to-speech)
  - `participant`: participant identity: P1 to P20
  - `RT`: reaction time [ms]

### RT-HS-P1.npy
- **Description**: This is a NumPy format file containing reaction time of participant P1 in HS test.
- **Content**: The data array has the shape `(2027, )`, where each element represents a time data(ms).

## Usage Example

### Python Example Code
Below is an example of how to load and use these data files in Python:

```python
import pandas as pd
import numpy as np

# Load CSV files
fgn_seq = pd.read_csv('data/FGN_0.5_30.csv')
random_chi_seq = pd.read_csv('data/Random_chisquare_30.csv')
reaction_seq = pd.read_csv('data/rsif20210272_si_002.csv')

# Load NumPy file
dataset = np.load('data/RT-HS-P1.npy')

# Print data summary
print("fgn_seq:")
print(fgn_seq.head())

print("\nrandom_chi_seq:")
print(random_chi_seq.head())

print("\nreaction_seq:")
print(reaction_seq.head())

print("\ndataset shape:", dataset.shape)
```

## Data Source
This dataset was collected and organized by ZhiQiang-Feng and SiYu-Feng for research related to verify the performances of the algorithms methioned in our paper.

## Contact
If you have any questions or suggestions regarding the dataset, please contact:

- Name: ZhiQiang Feng
- Email: z.q.feng@foxmail.com
- Institution: Hainan Normal University

