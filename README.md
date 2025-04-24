# Automatic Number Plate Recognition with YOLO and OCR

This project combines YOLO object detection with OCR technology to automatically detect and recognize license plates in images and video streams.

## Table of Contents
- [Features](#features)
- [Installation Guide](#installation-guide)
  - [Prerequisites](#prerequisites)
  - [Python 3.9 Installation](#python-39-installation)
  - [Project Setup](#project-setup)
- [Usage](#usage)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Features

- Real-time license plate detection using YOLO object detection
- Optical Character Recognition (OCR) for reading plate numbers
- Support for both image and video processing
- Web interface for easy access
- CSV export of recognized plate numbers
- Support for multiple plate formats

## Installation Guide

### Prerequisites

- Git
- Python 3.9
- Webcam (for real-time detection)

### Python 3.9 Installation

#### Windows
1. Download Python 3.9 from the [official Python website](https://www.python.org/downloads/release/python-3913/)
2. Run the installer
3. Check the box that says "Add Python 3.9 to PATH"
4. Click "Install Now"
5. Verify installation by opening Command Prompt and typing:
    ```
    python --version
    ```

#### macOS
1. Install Homebrew if not already installed:
    ```
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
2. Install Python 3.9 using Homebrew:
    ```
    brew install python@3.9
    ```
3. Verify installation:
    ```
    python3.9 --version
    ```

### Project Setup

#### 1. Clone the Repository
```bash
git clone https://github.com/Vinayak2k03/Automatic_Number_Plate_Recognition.git .
```

#### 2. Create and Activate Virtual Environment

##### Windows
```bash
python -m venv venv
venv\Scripts\activate
```

##### macOS/Linux
```bash
python3.9 -m venv venv
source venv/bin/activate
```

#### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

Note: If you encounter issues with PyTorch installation, you might need to install it separately following instructions at [PyTorch.org](https://pytorch.org/get-started/locally/).

#### 4. Run the Application

```bash
  python main.py
```

## Usage

- Press **ESC** key to exit the camera window
- For best results, ensure proper lighting conditions when capturing license plates
- The recognized plate numbers are saved in `ocr_results.csv` file

### Web Interface Options

The web interface provides several options:
- Upload image for processing
- View real-time camera feed
- Access detection history
- Configure detection parameters

### Command Line Options

```bash
python detect_plates.py --source 0  # Use webcam
python detect_plates.py --source video.mp4  # Process a video file
python detect_plates.py --source images/  # Process all images in a directory
```

## Configuration

You can modify the configuration in the `config.yaml` file:

```yaml
model:
  weights: 'weights/yolov5s.pt'
  confidence_threshold: 0.25
  
ocr:
  engine: 'tesseract'  # Options: tesseract, easyocr
  language: 'eng'
  
output:
  save_results: true
  display_window: true
```

## Troubleshooting

- **GPU-related errors**: Try running the application in CPU mode
  ```bash
  python detect_plates.py --device cpu
  ```
  
- **OCR-related issues**: Make sure all dependencies are correctly installed
  ```bash
  pip install pytesseract
  pip install opencv-python-headless
  ```
  
- **Model download failures**: Manually download the model files from the repository releases

- **Camera not working**: Check if your camera is properly connected and not being used by another application

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the terms specified in the LICENSE file.
