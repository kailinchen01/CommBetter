# CommBetter: Supporting Parents of Children with Communication Delays 

# Overview
The number of children diagnosed with developmental issues in Singapore is increasing. While there are more initiatives rolled out by the government to support them holistically (e.g., through increasing the quality and quantity of speech language therapists, subsidies for costs of care), there is less being done for parents themselves. Parents being the primary caregivers are well-placed to effect care and intervention but often lack the knowledge, lapse into non-beneficial behaviours (e.g., distracted by other matters), or forget the guidance from therapists, and need the right support to be able to do so.

We propose CommBetter, our system that analyses video for key non-verbal interactions between parent and child.

# Installation instructions
A virtual environment is recommended
python version 3.8 is recommended
```
conda create -n CommBetter python=3.8
conda activate CommBetter
```

### Set up MCGaze
Clone MCGaze repository 
```
Git clone https://github.com/zgchen33/MCGaze/tree/master
```
Install the following packages. Use the following versions for compatability with python version= 3.8
```
pip install torch==1.9.0+cu111 torchvision==0.10.0+cu111 torchaudio==0.9.0 -f https://download.pytorch.org/whl/torch_stable.html 
pip install mmcv-full==1.4.8 -f https://download.openmmlab.com/mmcv/dist/cu111/torch1.9.0/index.html 
```

Install MCGaze requirements
```
cd MCGaze
pip install -v -e .
```
Follow the instructions in MCGaze for model checkpoint set up.
Download checkpoint for yolov5 head detector from [link](https://drive.google.com/file/d/1gglIwqxaH2iTvy6lZlXuAcMpd_U0GCUb/view?usp=sharing)

### Directory Set Up
Create folders for demo run

```
cd MCGaze_demo
mkdir frames
mkdir new_frames
mkdir result/labels
```
Place 'run_system.ipynb' and 'combinecells.ipynb' in the same folder as MCGaze_demo.

### File paths Edit
In MCGaze_demo/head_det.py, edit file paths to the appropriate MCGaze model checkpoints.
In MCGaze_demoyolo_head/detect.py. edit file paths to the results folder previously created and yolo model checkpoint path.
In combinecells.ipynb, edits file paths to MCGaze model checkpoints.
In run_system.ipynb, edit file paths to your video.

###Run
Run all cells in run_system.ipynb. logs will be saved in the form of {video name}_gaze_gaze_behavior_log.txt. video results will be saved to processed_videos in the form of {video name}_results.mp4
