# 🎨 K-Means Image Color Quantization

This project implements the **K-Means clustering algorithm from scratch** in Python to perform **color quantization** on RGB images. Color quantization reduces the number of distinct colors in an image by clustering similar pixel colors and replacing them with a representative (mean) color.

## 📌 Objective

To reduce color complexity in an image while preserving visual quality, which helps in **image compression**, **storage optimization**, and **artistic stylization**.

## 🧠 What is K-Means?

K-Means is an unsupervised machine learning algorithm used for clustering. In the context of images:
- Each pixel is treated as a data point in 3D RGB space.
- Pixels are grouped into K clusters based on similarity.
- Each pixel is replaced by the average color of its assigned cluster.

## 🚀 How It Works

1. Randomly select `K` pixels from the image as initial centroids.
2. Assign each pixel to the closest centroid using Euclidean distance in RGB space.
3. Update each centroid by calculating the mean of all pixels assigned to it.
4. Repeat the assignment and update steps until convergence or a max number of iterations.
5. Generate a new image using the final cluster centroids.

## 🔬 Results and Observations

The algorithm was tested on a facial image using the following `K` values:  
**K = 2 to 10, 15, 20**

| K Value | Observation |
|--------|-------------|
| 2 - 4 | Image becomes stylized with major color blocks. High compression, low detail. |
| 5 - 7 | Gradual reappearance of finer color details and structure. |
| 8 - 10 | Good balance between color reduction and visual quality. |
| 15, 20 | Very close to the original image, minimal perceptual difference, higher computation. |

## 📊 Visual Results

Sample quantized images are available in the `results/` folder.

## 🧑‍💻 Implementation Details

The algorithm is implemented in a class named `k_means` with the following methods:

- `__init__`: Initializes centroids and reshapes the image data.
- `euclidean_distance`: Computes Euclidean distance between two RGB vectors.
- `assign_clusters`: Assigns each pixel to the nearest centroid.
- `update_centroids`: Updates centroid positions based on current pixel assignments.
- `k_means`: Runs the algorithm for a fixed number of iterations or until convergence.
- `generate_image`: Reconstructs the quantized image from the final centroids.

## 🛠️ Requirements

- Python 3.x
- numpy
- OpenCV (`cv2`)
- matplotlib (for displaying results)
