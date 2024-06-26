# SIFT-based Logo Detection and Product Classification

This script performs SIFT-based logo detection and classification of food products as either Bio or Non-Bio by comparing product images to a given logo. The output is saved in a JSON file.

## Requirements

Ensure you have the following Python libraries installed:
- `cv2` (OpenCV)
- `numpy`
- `matplotlib`
- `requests`

You can install these dependencies using pip:
```bash
pip install opencv-python numpy matplotlib requests
```

## Input

The script requires two inputs from the user:
1. `input_file_name`: JSON file containing the product data.
2. `input_logo_file`: Image file of the logo to detect (e.g., `Bio_logo.png` or `rainforest_logo.png`).

## Script Overview

### Functions


#### download_image(url)
- Downloads an image from a given URL.

#### detect_SIFT_keypoints(image)
- Detects SIFT keypoints and computes descriptors for an image.

#### match_keypoints(descriptors1, descriptors2)
- Matches SIFT descriptors between two images and applies a ratio test.

#### verify_matches(image1, image2, keypoints1, keypoints2, matches, i)
- Verifies matches using contour area comparison.

#### classify_product(images, logo_images, Iscount)
- Classifies products based on the number of verified matches.

#### read_product_image(url)
- Downloads and reads the product image and the logo image.

#### split_color_filter(product_image, logo_image)
- Splits images into their color channels.

### Main Function

The `main_function` processes the combined product data:
- Iterates through the product data.
- Downloads product images and the logo image.
- Splits images into color channels.
- Classifies products as Bio or Non-Bio.
- Saves the classification results to the JSON data.

### Output

The script updates the JSON file with the classification results:
- `SIFT_ContourArea_detection`: The classification result (Bio or Non-Bio).
- `SIFT_ContourArea_detection_colormatch`: Number of color matches.
- `SIFT_ContourArea_detection_verifymatch`: Number of verified matches.

### Structure of Code

![Project Logo](/structure.png)

## License

This script is provided as-is without any warranties. Use it at your own risk.
