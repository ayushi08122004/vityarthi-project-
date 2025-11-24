🤸 Human Pose Estimation using MediaPipe

🌟 Project Title

Real-Time Vision: Human Pose Estimation on Static Images

📖 Overview of the Project

This project implements a foundational computer vision application for Human Pose Estimation. It utilizes Google's MediaPipe Pose solution to accurately detect 33 key anatomical landmarks (joints) on a human subject within a static image.

The pipeline involves loading an image, running it through the MediaPipe machine learning model, and then visualizing the detected skeleton and landmarks. The code also demonstrates how to extract the raw numerical coordinates of specific joints (e.g., wrists) to perform quantitative analysis, such as calculating the distance between two body parts.

✨ Features

33-Point Landmark Detection: Accurately identifies 33 key joints on the body (head, shoulders, elbows, wrists, hips, etc.).

Skeleton Visualization: Draws the full skeletal structure and landmarks directly onto the input image.

Coordinate Extraction: Converts normalized landmark coordinates (0.0 to 1.0) into absolute pixel values.

Quantitative Analysis: Includes an example calculation (distance between wrists) based on the extracted coordinates.

Robust Setup: Uses specific, pinned library versions for guaranteed compatibility in environments like Google Colab.

🛠️ Technologies/Tools Used

Tool/Technology

Role

Python 3

Core programming language.

MediaPipe (0.10.14)

The machine learning framework for high-accuracy pose inference.

OpenCV (cv2)

Used for image loading, manipulation, and BGR $\leftrightarrow$ RGB color space conversion.

NumPy (<2)

Essential for numerical operations and coordinate distance calculations.

Matplotlib

Used for displaying the original and annotated images in the notebook environment.

Google Colab/Jupyter

The primary execution environment (supports magic commands like %pip).

⚙️ Steps to Install & Run the Project

This project is optimized for running in a Jupyter Notebook or Google Colab environment.

1. Setup and Dependencies

The project requires specific library versions for stability. These can be installed using the following command in a notebook cell:

# Install specific, known-good versions to avoid dependency conflicts
%pip install numpy"<2" mediapipe==0.10.14 opencv-contrib-python==4.9.0.80 matplotlib


2. Prepare the Image

Before running the core script, ensure your test image is accessible.

Image Path: The script currently expects an image at a path like /content/assest/Screenshot 2025-11-24 195851.png.

Action: Replace the default image_path variable in the code with the actual path to your desired image file. If running in Colab, you may need to upload the image or mount your Google Drive.

3. Execution

Run the Python script cells in sequence. The script automatically handles:

Loading the image.

Converting the image color space (BGR $\to$ RGB).

Initializing the MediaPipe Pose model (static_image_mode=True).

Processing the image and detecting landmarks.

Visualizing the result and printing coordinate data to the console.

🧪 Instructions for Testing

To confirm the project is running correctly, follow these steps:

Run the Setup Cell: Verify that all libraries are installed without error.

Load Image: Ensure the display_image("Original Image", ...) function successfully displays your input image. If it fails, check the image_path.

Check Annotation: Inspect the Pose Landmarks and Connections output image. The subject's body should be overlaid with 33 distinct blue dots (landmarks) connected by green lines (connections/skeleton). 4.  Verify Coordinates: Look at the console output for the numerical results. You should see:

Pixel coordinates for the Left and Right Wrist (e.g., Left Wrist Pixel Coordinates: (x=500, y=320)).

The calculated Pixel distance between wrists (a floating-point number).

If the annotated image is correctly rendered and coordinates are printed, the Pose Estimation model is functioning as expected.# vityarthi-project-
