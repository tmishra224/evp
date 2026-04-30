# evp workspace

This repository is minimal. Steps to build and test locally on Windows PowerShell:

1. Open PowerShell and change to the project folder:

```powershell
Set-Location d:\CLG\evp
```

2. Create and activate a virtual environment:

```powershell
python -m venv .venv
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
.\.venv\Scripts\Activate.ps1
```

3. Upgrade pip and install dependencies:

```powershell
python -m pip install --upgrade pip setuptools wheel
pip install -r requirements.txt
```

4. Run the smoke test (from the repo root):

```powershell
python -c "from ultralytics import YOLO; import cv2; print('ultralytics OK, cv2', cv2.__version__)"
```

Notes:
- For GPU support, install a matching PyTorch wheel from https://pytorch.org/ after selecting the correct CUDA version.
- If `python` is not recognized, install Python 3.8+ and ensure it's on your PATH.
