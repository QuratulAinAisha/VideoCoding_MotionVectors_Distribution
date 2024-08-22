# Deriving Motion Vector Distribution in YUV Sequence

This project implements a block-based motion estimation algorithm to compute and visualize motion vector distributions in a YUV video sequence. The output is a 3D histogram that shows the distribution of motion vectors between consecutive frames in the video.

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Requirements](#requirements)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Code Structure](#code-structure)

## Introduction

Motion estimation is a key process in video compression algorithms, such as MPEG and H.264, where the goal is to estimate the movement of objects between consecutive frames of a video. This project performs motion estimation by dividing frames into blocks and finding the block's best match in the next frame using a Sum of Squared Differences (SSD) metric. The motion vectors between consecutive frames are then visualized in a 3D plot showing their distribution.

The YUV video format is commonly used in video compression. In this project, we process the Y channel (luminance) of YUV frames to derive motion vectors.

## Features

- **YUV Frame Processing**: Extracts the Y channel from YUV video sequences.
- **Block-based Motion Estimation**: Estimates motion vectors using the SSD metric.
- **3D Histogram Visualization**: Visualizes the distribution of motion vectors in a 3D bar plot.
  
## Requirements

- **Python 3.x**
- **NumPy** for numerical operations
- **Matplotlib** for 3D plotting

## Installation

To install the required dependencies, run the following command:

```bash
pip install numpy matplotlib
```

## Usage

1. Place the YUV video file in the appropriate location. Update the `filename`, `width`, `height`, and `num_frames` variables in the script accordingly.

2. Run the script with the following command:

   ```bash
   python motion_vector_distribution.py
   ```

3. After execution, the script will display a 3D histogram of the motion vector distribution for the given video sequence.

## Code Structure

### `read_yuv_frames`

This function reads the YUV frames from a given video file and extracts the Y channel (luminance) for each frame. The Y channel is converted into grayscale and stored for motion estimation.

```python
def read_yuv_frames(filename, width, height, num_frames):
    # Reads YUV frames from the file and returns the grayscale Y channel
```

### `motion_estimation`

This function performs block-based motion estimation on the extracted grayscale frames. The image is divided into blocks, and for each block in the current frame, the best matching block in the next frame is found using the SSD (Sum of Squared Differences) metric.

```python
def motion_estimation(frames, block_size=32, search_area=16):
    # Computes motion vectors for consecutive frames using block matching
```

### Visualization

The computed motion vectors are visualized in a 3D bar plot using Matplotlib's `bar3d` function. The plot shows the frequency of different motion vector values over the sequence of frames.

```python
# 3D histogram visualization of motion vectors
plt.show()
```

### Parameters

- **`block_size`**: Size of the blocks for motion estimation (default: 32).
- **`search_area`**: Size of the area in which to search for a matching block in the next frame (default: 16).

