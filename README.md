# bgral

[![PyPI - Version](https://img.shields.io/pypi/v/bgral?color=blue)](https://pypi.org/project/bgral/)
[![Status - Alpha](https://img.shields.io/badge/status-alpha-orange)](https://pypi.org/project/bgral/)
[![License - MIT](https://img.shields.io/badge/license-MIT-green)](#license)

**bgral** is a Python library currently under active development. The PyPI package has been published to reserve the name.  

At the moment, it contains only a couple of basic utility functions — but more features are on the way!

---

## ✨ Features (So Far)

### `made_by()`
Returns the author's name.

```python
from bgral.core import made_by

print(made_by())  # Output: Bhavya Gujral
```

---

# 🎨 Video Style Transfer

This project applies neural style transfer on videos by extracting individual frames, applying style transfer to each frame, and then reassembling the frames into a stylized video with the original audio.

## 🚀 Features

- Extracts frames from a video.
- Applies style transfer on each frame using a pre-trained TensorFlow model.
- Recompiles the stylized frames back into a video.
- Adds original audio to the final video.
- Supports both local (offline) and online (TensorFlow Hub) style transfer models.

## 🛠 Prerequisites

To run this project, you will need:

- Python 3.x  
- TensorFlow  
- OpenCV  
- TensorFlow Hub  
- PIL (Python Imaging Library)  
- ffmpeg (for adding audio back to the video)

## 📦 Install Dependencies

Install Python libraries:

```bash
pip install tensorflow opencv-python tensorflow-hub pillow
```

Install `ffmpeg` (Linux):

```bash
sudo apt install ffmpeg
```

## 🧪 Usage

### Running the Script

To apply style transfer on a video, use the `style_transfer()` function:

```python
from bgral.video_style_transfer import style_transfer

style_transfer(
    input_video="input.mp4",
    style_image_path="style.jpg",
    working_dir="output",
    fps=30
)
```

### Arguments:

- `input_video (str)`: Path to the input video file.
- `style_image_path (str)`: Path to the image to be used for style transfer.
- `working_dir (str)`: Directory where the frames, styled frames, and final video will be saved.
- `fps (int)`: Frames per second for the output video (default is 30).

### How It Works

1. **Extract Frames**: The video is broken down into individual frames.
2. **Apply Style Transfer**: The style image is applied to each frame using a pre-trained model from TensorFlow Hub.
3. **Recompile Video**: The stylized frames are then compiled into a new video.
4. **Add Audio**: The original audio from the input video is added back to the final stylized video.

# Understanding FPS Calculation Based on Video Duration

In video processing, **FPS (Frames Per Second)** refers to the number of frames displayed or captured per second of video. To calculate the FPS of a video, you can use the formula:

fps = len(frame_paths) / video_duration_in_seconds

Where:
- `len(frame_paths)` is the total number of frames in the video.
- `video_duration_in_seconds` is the total duration of the video in seconds.

### Example:
Let's say the video has a total duration of 11 seconds, and there are 250 frames extracted from the video. To calculate the FPS, we use the formula:

fps = 250 / 11

This results in:

fps ≈ 22.73

So, the video has approximately **22.73 FPS**, meaning it displays about **22.73 frames per second**. This FPS determines the smoothness of the video, with a higher FPS providing smoother video playback and a lower FPS resulting in choppier motion, especially during fast scenes.

### Conclusion:
For this example, the FPS is approximately **22.73 FPS** for a video that is 11 seconds long and has 250 frames. By using this simple formula, you can calculate the FPS for any video by knowing the total number of frames and the video duration.


### 🧪 Example

Run the following command to execute the style transfer process on a sample video:

```bash
python check.py
```

This will read the video `test.mp4`, apply the style from `test.jpg`, and save the output to the `output/` folder.

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
