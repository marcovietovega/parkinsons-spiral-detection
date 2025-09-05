# Parkinson's Disease Detection with Hand-Drawn Spirals

This project uses machine learning techniques to identify Parkinson's Disease in patients by analyzing their hand-drawn spiral patterns. It uses two different approaches to study the drawings and can identify patients with high accuracy.

## Why This Matters

Early detection of Parkinson's Disease can dramatically improve patients' quality of life. Traditional diagnosis often relies on visible symptoms that appear years after the disease has already progressed significantly. By the time tremors become obvious, many brain cells have already been lost.

This project offers hope for earlier, more accessible screening. A simple spiral drawing test could be administered in any doctor's office or even at home using a tablet. The beauty lies in its simplicity: no expensive equipment, no invasive procedures, just a pen and paper.

This technology could be especially valuable in underserved communities where specialized neurologists aren't readily available. The project demonstrates how artificial intelligence can transform a basic human task into a powerful diagnostic tool, making advanced medical screening accessible to everyone.

### Key Features of This Project

- **Two Different Approaches**: Studies both the tremor patterns and the visual appearance of spiral drawings.
- **Signal Processing**: Finds tremor patterns in hand movement data.
- **Image Generation**: Converts coordinate data into images that neural networks can analyze.
- **Robust Testing**: Uses cross-validation to ensure reliable results.
- **Excellent Performance**: Achieved 100% accuracy with the frequency-based approach.

## Dataset

The data comes from people drawing spirals with a digital pen. During drawing, the system records pen coordinates (x, y) and timestamps. The dataset includes:

- Healthy controls: Participants without Parkinson's Disease
- Parkinson's patients: Participants diagnosed with Parkinson's Disease

Each drawing session produces a sequence of coordinate points that represent pen movement during spiral tracing.

## How the Models Work

The project uses **two different approaches** to analyze spiral drawings:

**Method 1 - Frequency Analysis**: Analyzes tremor patterns in the movement data.

- Calculates pen movement speed from coordinates and timestamps
- Uses Fast Fourier Transform to identify tremor characteristics
- Focuses on the 1-10 Hz frequency range (typical tremor frequencies)
- Measures speed variability throughout the drawing

**Method 2 - Image Classification**: Converts drawings into images and analyzes visual patterns.

- Generates 224x224 pixel images from coordinate data
- Applies data augmentation (rotation, flipping, color changes)
- Uses a convolutional neural network
- Employs 5-fold cross-validation for reliable evaluation

### The Two Models

1. **Linear Discriminant Analysis (LDA)**: Analyzes frequency patterns in movement data.
2. **Convolutional Neural Network (CNN)**: Recognizes visual patterns in spiral images.

## Tools and Techniques

### Computer Programs Used

- **PyTorch**: Deep learning framework for building and training neural networks, specifically the CNN model.
- **torchvision**: Computer vision library with tools for image processing and data transformations.
- **scikit-learn**: Machine learning tools including the Linear Discriminant Analysis model.
- **scipy**: Math tools for signal processing and Fourier transform analysis.
- **pandas/numpy**: For working with data and numbers.
- **matplotlib/seaborn**: For making charts and graphs.
- **PIL**: Python Imaging Library for creating and processing spiral images.

### Methods Used

- **Feature engineering**: Creates meaningful features like dominant frequency and speed variability from raw coordinates.
- **Signal processing**: Identifies tremor patterns in drawing data using Fourier transforms.
- **Cross-validation**: Tests models using multiple data splits for reliable evaluation.
- **Data augmentation**: Generates additional training examples by transforming images.

## Results

- **Perfect LDA Performance**: The frequency-based model achieved 100% accuracy.
- **Strong CNN Performance**: The image-based model achieved 92% accuracy.
- **Comprehensive Metrics**: Both models show excellent precision, recall, and F1-scores.
- **Clinical Relevance**: The frequency features align with known Parkinson's tremor patterns.

| Model                 | Accuracy | Healthy Precision | Healthy Recall | Parkinson's Precision | Parkinson's Recall |
| --------------------- | -------- | ----------------- | -------------- | --------------------- | ------------------ |
| LDA (Frequency-based) | 100%     | 1.00              | 1.00           | 1.00                  | 1.00               |
| CNN (Image-based)     | 92%      | 1.00              | 0.80           | 0.88                  | 1.00               |

## What This Project Shows

### Working with Data

- **Smart data handling**: Processes spiral drawings and extracts coordinate information effectively.
- **Feature engineering**: Creates new meaningful features like dominant frequency and speed variability from raw drawing data.
- **Pattern finding**: Finds meaningful shaking patterns in tremor data using signal processing.
- **Picture making**: Turns movement data into pictures computers can read using PIL image processing.

### Building Models

- **Two different approaches**: Uses both shaking analysis and picture recognition.
- **Careful testing**: Makes sure the models work well on new data.
- **Medical focus**: Uses information that doctors find important.
- **High success**: Both models work very well at identifying patients.

## What I Learned

This project shows important computer science and medical skills:

- **Using Two Methods**: Combining shaking analysis with picture recognition for better results.
- **Feature Engineering**: Creating new meaningful features (dominant frequency, speed variability) from raw coordinate data.
- **Signal Analysis**: Using math to find meaningful patterns in movement data.
- **Deep Learning**: Building and training neural networks with PyTorch for image classification.
- **Proper Testing**: Making sure models work well on new patient data.
- **Smart Features**: Creating useful measurements from basic drawing coordinates.

## Contact

Marco Vieto Vega - [vietomarc@myvuw.ac.nz](mailto:vietomarc@myvuw.ac.nz)

---

_This project was developed as part of DATA471 coursework at Victoria University of Wellington._
