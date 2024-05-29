# Ultimate Vocal Remover GUI v5.6 (Experimental Unofficial IPEX fork)
<img src="https://raw.githubusercontent.com/Anjok07/ultimatevocalremovergui/master/gui_data/img/UVR_v5.6.png?raw=true" />

## What is this fork?
This fork is to utilize intel oneAPI extensions for PyTorch on linux based systems.

Currently, this has only been tested with Arch(EndeavourOS) with the intel-oneapi-basekit package from staging (2024.1)

Models that have the ONNX extension will still utilize your CPU. ckpt/pth models have been confirmed as working.

## About

This application uses state-of-the-art source separation models to remove vocals from audio files. UVR's core developers trained all of the models provided in this package (except for the Demucs v3 and v4 4-stem models).

- **Core Developers**
    - [Anjok07](https://github.com/anjok07)
    - [aufr33](https://github.com/aufr33)

- **Support the Project**
    - [Donate](https://www.buymeacoffee.com/uvr5)


### Linux Installation

<details id="LinuxInstall">
  <summary>See Linux Installation Instructions</summary>

<br />
    
**These install instructions are for Arch based Linux systems.**

- Download and save this repository [here](https://github.com/7rident/ultimatevocalremovergui-ipex/archive/refs/heads/master.zip)
- From the saved directory run the following commands in this order 

**For Arch Based (EndeavourOS):**

Python 3.10 is STRONGLY recommended for this. I have no guarantees that this will work with any other versions of python.

```
sudo pacman -Syu
sudo pacman -Sy
sudo pacman -S intel-oneapi-basekit
sudo pacman -S python-pip
sudo pacman -S --noconfirm tk
sudo pacman -S ffmpeg
```

create, activate, and install dependencies for a virtual environment in your UVR5 directory by typing:

```
python3.10 -m venv venv
source venv/bin/activate
pip install -r requirements-ipex.txt
```
Remember to set your oneAPI variables before launching by typing:

```
source /opt/intel/oneapi/setvars.sh
```

After all previous commands are set, start the application by typing:

```
python UVR5.py
```

</details>

### Other Application Notes
- This application is only compatible with 64-bit platforms. 
- This application relies on the Rubber Band library for the Time-Stretch and Pitch-Shift options.
- This application relies on FFmpeg to process non-wav audio files.
- The application will automatically remember your settings when closed.
- Conversion times will significantly depend on your hardware. 
- These models are computationally intensive.

### Performance:
- Model load times are faster.
- Importing/exporting audio files is faster.

## Troubleshooting

### Common Issues

- If FFmpeg is not installed, the application will throw an error if the user attempts to convert a non-WAV file.
- Memory allocation errors can usually be resolved by lowering the "Segment" or "Window" sizes.

#### MacOS Sonoma Left-click Bug
There's a known issue on MacOS Sonoma where left-clicks aren't registering correctly within the app. This was impacting all applications built with Tkinter on Sonoma and has since been resolved. Please download the latest version via the following link if you are still experiencing issues - [link](https://github.com/Anjok07/ultimatevocalremovergui/releases/tag/v5.6)

This issue was being tracked [here](https://github.com/Anjok07/ultimatevocalremovergui/issues/840).

### Issue Reporting

Please be as detailed as possible when posting a new issue. 

If possible, click the "Settings Button" to the left of the "Start Processing" button and click the "Error Log" button for detailed error information that can be provided to us.

## License

The **Ultimate Vocal Remover GUI** code is [MIT-licensed](LICENSE). 

- **Please Note:** For all third-party application developers who wish to use our models, please honor the MIT license by providing credit to UVR and its developers.

## Credits
- [ZFTurbo](https://github.com/ZFTurbo) - Created & trained the weights for the new MDX23C models. 
- [DilanBoskan](https://github.com/DilanBoskan) - Your contributions at the start of this project were essential to the success of UVR. Thank you!
- [Bas Curtiz](https://www.youtube.com/user/bascurtiz) - Designed the official UVR logo, icon, banner, and splash screen.
- [tsurumeso](https://github.com/tsurumeso) - Developed the original VR Architecture code. 
- [Kuielab & Woosung Choi](https://github.com/kuielab) - Developed the original MDX-Net AI code. 
- [Adefossez & Demucs](https://github.com/facebookresearch/demucs) - Developed the original Demucs AI code. 
- [KimberleyJSN](https://github.com/KimberleyJensen) - Advised and aided the implementation of the training scripts for MDX-Net and Demucs. Thank you!
- [Hv](https://github.com/NaJeongMo/Colab-for-MDX_B) - Helped implement chunks into the MDX-Net AI code. Thank you!
- [intel](https://github.com/intel/intel-extension-for-pytorch) - Providing the libraries that make things tick for Intel Arc GPUs
## Contributing

- For anyone interested in the ongoing development of **Ultimate Vocal Remover GUI**, please send us a pull request, and we will review it. 
- This project is 100% open-source and free for anyone to use and modify as they wish. 
- We only maintain the development and support for the **Ultimate Vocal Remover GUI** and the models provided. 

## References
- [1] Takahashi et al., "Multi-scale Multi-band DenseNets for Audio Source Separation", https://arxiv.org/pdf/1706.09588.pdf
