# Face Recognition System

A simple Python-based face recognition application that identifies faces from a set of training images.

## Features
- Trains on-the-fly using images in the `train/` directory.
- Detects and recognizes faces in a test image.
- Draws bounding boxes and labels names on the output.

## Prerequisites

- Python 3.x
- `dlib` (C++ toolkit required by `face_recognition`)

## Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd <repository-name>
    ```

2.  **Install Dependencies:**

    **For Linux/macOS:**
    ```bash
    pip install face_recognition opencv-python numpy
    ```

    **For Windows (Important):**
    Installing `dlib` on Windows can be tricky. If the standard `pip install face_recognition` fails, follow these steps:

    a. **Install pre-compiled dlib wheel:**
       You need a version of `dlib` compatible with your Python version. For Python 3.12, use:
       ```bash
       pip install https://github.com/z-mahmud22/Dlib_Windows_Python3.x/raw/main/dlib-19.24.99-cp312-cp312-win_amd64.whl
       ```
       *(Search online for "dlib wheel python [your_version]" if you are not using 3.12)*

    b. **Install other dependencies:**
       ```bash
       pip install "numpy<2" opencv-python face_recognition
       ```
       > **Note:** We specify `numpy<2` because `dlib` binary wheels currently have compatibility issues with Numpy 2.0+.

## Usage

1.  **Prepare Training Data:**
    Place images of known people in the `train/` directory. The filename (excluding extension) will be used as the person's name (e.g., `ross.jpg` -> "Ross").

2.  **Run the Application:**
    Ensure you have a test image at `./test/test.jpg` (or modify `main.py` to point to your image).
    ```bash
    python main.py
    ```

3.  **View Results:**
    - A window will pop up showing the recognized faces.
    - The result is also saved as `output.jpg`.

## Project Structure

- `main.py`: The main script for training and recognition.
- `train/`: Directory containing images for training the model.
- `test/`: Directory containing images to test the recognition.
