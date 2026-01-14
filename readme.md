# Face Swapping Tool

A powerful and easy-to-use face swapping application that leverages advanced deep learning techniques to seamlessly swap faces in images and videos.

## Features

- **High-Quality Face Swapping**: Advanced AI-powered face detection and swapping
- **Format Support**: Works with PNG images
- **Real-time Processing**: Fast processing with optimized algorithms
- **User-Friendly Interface**: Simple and intuitive GUI for easy usage
- **Cross-Platform**: Supports macOS, Windows, and Linux

## System Requirements

### Minimum Requirements
- **RAM**: 4GB (8GB+ recommended)
- **Disk Space**: 2GB for dependencies
- **GPU**: NVIDIA GPU with CUDA support (optional but recommended for faster processing)

### Python Requirements
- Python 3.7 or higher

## Installation

Choose the setup instructions for your operating system:

### macOS

1. **Install Homebrew** (if not already installed):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Install Python 3 and Dependencies**:
   ```bash
   brew install python3
   brew install git
   ```

3. **Clone the Repository**:
   ```bash
   git clone https://github.com/variedlark/Face-Swapping-Tool.git
   cd Face-Swapping-Tool
   ```

4. **Create a Virtual Environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

5. **Install Python Dependencies**:
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

6. **Create The Wig**:
   ```bash
   python prepare_wig.py
   ```

7. **Run The Tool**:
   ```bash
   python run_filter.py
   ```

### Windows

1. **Install Python 3**:
   - Download from https://www.python.org/downloads/
   - **Important**: Check "Add Python to PATH" during installation
   - Verify installation by opening Command Prompt and running:
     ```cmd
     python --version
     ```

2. **Install Git** (if not already installed):
   - Download from https://git-scm.com/download/win

3. **Clone the Repository**:
   ```cmd
   git clone https://github.com/variedlark/Face-Swapping-Tool.git
   cd Face-Swapping-Tool
   ```

4. **Create a Virtual Environment**:
   ```cmd
   python -m venv venv
   venv\Scripts\activate
   ```

5. **Install Python Dependencies**:
   ```cmd
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```

6. **Create The Wig**:
   ```cmd
   python prepare_wig.py
   ```

7. **Run The Tool**:
   ```cmd
   python run_filter.py
   ```

### Linux (Ubuntu/Debian-based)

1. **Update System Packages**:
   ```bash
   sudo apt-get update
   sudo apt-get upgrade -y
   ```

2. **Install Python 3 and Dependencies**:
   ```bash
   sudo apt-get install -y python3 python3-pip python3-venv
   sudo apt-get install -y git
   ```

3. **Clone the Repository**:
   ```bash
   git clone https://github.com/variedlark/Face-Swapping-Tool.git
   cd Face-Swapping-Tool
   ```

4. **Create a Virtual Environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

5. **Install Python Dependencies**:
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

6. **Create The Wig**:
   ```bash
   python prepare_wig.py
   ```

7. **Run The Tool**:
   ```bash
   python run_filter.py
   ```

### Linux (Fedora/RHEL-based)

1. **Update System Packages**:
   ```bash
   sudo dnf update -y
   ```

2. **Install Python 3 and Dependencies**:
   ```bash
   sudo dnf install -y python3 python3-pip python3-devel
   sudo dnf install -y git
   ```

3. **Clone the Repository**:
   ```bash
   git clone https://github.com/variedlark/Face-Swapping-Tool.git
   cd Face-Swapping-Tool
   ```

4. **Create a Virtual Environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

5. **Install Python Dependencies**:
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

6. **Create The Wig**:
   ```bash
   python prepare_wig.py
   ```

7. **Run The Tool**:
   ```bash
   python run_filter.py
   ```

## Quick Start

1. **Select Images/Video**:
   - Choose the source image (face to swap from)
   - Make sure to place it in the "assets" folder
   - Make sure to name it "mask.png"
  
2. **Create The Wig**:
   ```bash
   python prepare_wig.py
   ```

3. **Run The Tool**:
   ```bash
   python run_filter.py
   ```
4- **Enjoy**

## GPU Support (NVIDIA)

For faster processing with an NVIDIA GPU:

1. **Install CUDA Toolkit**: https://developer.nvidia.com/cuda-downloads
2. **Install cuDNN**: https://developer.nvidia.com/cudnn
3. **Install GPU-enabled dependencies**:
   ```bash
   pip install tensorflow-gpu
   # or
   pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
   ```

## Troubleshooting

### Common Issues

**Issue**: `ModuleNotFoundError: No module named 'cv2'`
- **Solution**: Run `pip install opencv-python`

**Issue**: `CUDA not found` (GPU mode)
- **Solution**: Verify CUDA installation and install `tensorflow-gpu` or `torch` GPU version

**Issue**: Permission denied on macOS/Linux
- **Solution**: Run `chmod +x main.py` before executing

**Issue**: Python not found on Windows
- **Solution**: Ensure Python was added to PATH during installation. Reinstall Python and check "Add Python to PATH"

## Performance Tips

- Use GPU acceleration if available (significantly faster)
- Reduce input image resolution for quicker processing
- Close unnecessary applications to free up RAM
- Ensure adequate storage space for output files

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For issues, questions, or suggestions:
- Open an issue on the GitHub repository
- Check the troubleshooting section above
- Ensure all dependencies are properly installed

## Disclaimer

This tool is designed for ethical and legal purposes. Users are responsible for ensuring that face swapping is performed with proper consent and in compliance with local laws and regulations.

---

**Last Updated**: January 14, 2026
