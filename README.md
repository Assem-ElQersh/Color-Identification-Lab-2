<div align="center">

# Color Identification in Images using LAB Color Space (Kaggle Edition)
Check the [Kaggle notebook](https://www.kaggle.com/code/assemelqirsh/color-identification-in-images)

</div>

This project uses OpenCV and the LAB color space to identify colors in images for improved perceptual accuracy. Unlike the [original version](https://github.com/Assem-ElQersh/Color-Identification-Lab), this implementation works in environments without interactive display capabilities (like Kaggle notebooks).

## Features

- **Grid-based Color Sampling**: Automatically samples colors at evenly spaced points across the image
- **Dominant Color Analysis**: Uses K-means clustering to identify the most common colors in the image
- **LAB Color Space Matching**: Matches colors using the perceptually uniform LAB color space for better results
- **No Interactive Dependencies**: Works in non-interactive environments like Kaggle notebooks
- **Comprehensive Color Analysis**: Provides both point-based and dominant color identification
- **Visualization Tools**: Creates visual representations of identified colors and their distribution

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Assem-ElQersh/Color-Identification-Lab-2.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Color-Identification-Lab-2
   ```
3. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```

## Usage in Kaggle

1. Create a new notebook on Kaggle
2. Add the "colour-detection-using-pandas-opencv" dataset to your notebook
3. Copy the contents of `kaggle_color_identifier.py` into your notebook
4. Run the notebook to analyze colors in your images

## Local Usage

```python
# Import the module
from color_identifier import analyze_image

# Analyze an image
analyze_image('path/to/your/image.jpg')
```

## How It Works

### Color Identification Process

1. **Loading Color Data**: The program loads a database of named colors with their RGB values
2. **Image Processing**: The input image is loaded and processed using OpenCV
3. **Grid-based Sampling**: Colors are sampled at regular intervals across the image
4. **LAB Color Matching**: Each sampled color is converted to the LAB color space and matched against the database
5. **Dominant Color Analysis**: K-means clustering identifies the most common colors in the image
6. **Visualization**: Results are displayed using matplotlib with the original image and color information

### LAB Color Space

The LAB color space consists of:
- L: Lightness from black (0) to white (100)
- a: Color from green (-) to red (+)
- b: Color from blue (-) to yellow (+)

Using LAB space for color comparison provides more perceptually accurate results than direct RGB comparison.

## Example Output

The program produces two types of visual outputs:

1. **Grid-based Color Analysis**:
   - Shows the original image with sampling points
   - Displays color names and RGB values for each sampled point

2. **Dominant Color Analysis**:
   - Shows the most common colors in the image
   - Displays color names, RGB values, and frequency percentages

## Customization

You can modify these parameters to adjust the analysis:

```python
# Change the number of sampling points
color_results = identify_colors_in_image(image, colors_df, num_points=7)  # Default is 5

# Adjust the number of dominant colors to find
dominant_colors = analyze_dominant_colors(image, colors_df, k=8)  # Default is 5
```

## Applications

- **Graphic Design**: Identify color schemes from inspiration images
- **Image Analysis**: Extract and quantify color information from photographs
- **Data Visualization**: Generate color palettes based on dominant colors
- **UI/UX Design**: Create harmonious color schemes based on reference images
- **Digital Art**: Analyze color composition in artworks

## Advantages Over Original Implementation

- **Non-interactive**: Works in environments without display capabilities (like Kaggle)
- **Automatic Processing**: No manual clicking required to identify colors
- **Comprehensive Analysis**: Provides both point-based and overall color analysis
- **Better Visualization**: Creates clear visual representations of color information
- **Robust Error Handling**: Handles missing files or incorrect paths gracefully

## Example

![Example](https://github.com/user-attachments/assets/464e2593-9a5a-4aad-8da6-149e125c3950)

*The above image shows an example of the [original project](https://github.com/Assem-ElQersh/Color-Identification-Lab). The new implementation produces similar results but with automated color sampling.*

## License
This project is licensed under the MIT License - see the [LICENSE](https://github.com/Assem-ElQersh/Color-Identification-Lab-2/blob/main/LICENSE) file for details.
