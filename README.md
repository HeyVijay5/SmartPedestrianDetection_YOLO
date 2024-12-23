## Table of Contents
- [Prerequisites](#prerequisites)
    - [Environment](#environment)
    - [Video Description](#video-description)
- [Modules](#modules)
    - [User Interface](#tkmodule)
    - [Region of Interest Selector](#roi)
    - [YOLO Model](#yolo)
    - [Working of the Detection Code](#code)
    - [Result Visualisation](#visualisation)
    - [Result - Annotated Video](#result)
- [Working Demo](#demo)

- [Developers](#developers)
- [Links](#links)
- [References](#references)            

## Prerequisites <a name='prerequisites'></a>

### Environment <a name='environment'></a>

1. Python 3 Environment
2. Python modules required: NumPy, Pandas, PyTorch, Opencv2, Matplotlib, Ultralytics, Supervision, Tkinter, TQDM

OR
- Any Python3 IDE installed with the above modules. (Pycharm is used in the development of this project)

### Video Description <a name='video-description'></a>

The tool supports the usage of timelapse videos of any kind and any size with a good resolution and frame rate. Optimize your frame rate and quality of the video based on how big are the persons in the video(Smaller persons in the frame require the video to be clearer).
The video used during the development and testing of the model is a timelapse video of a place on the campus of UMass Lowell which contains multiple paths on which the number of people passing has to be counted.

##### Test Video Information 

- Height - 720
- Width - 1280
- Frame Rate - 30 FPS
- Timelapse Rate - 1 Hour/minute

https://github.com/kysgattu/Pedestrain-Detection-System/assets/42197976/7b929dc9-bdb4-4b71-9ef2-a800f3e86184

## Modules<a name='modules'></a>

> ### User Interface <a name = 'tkmodule'></a>

The Front-End UI is a Tkinter Dialog box where 
- A video file on which the person detection is to be performed can be browsed from the File System. 
- A Target location on the file system where the result annotated video has to be saved
- Number of Regions of Interest on which the detection has to be performed
- Names for each Region of Interest

<img width="1280" alt="Screenshot 2023-11-16 at 7 35 35 PM" src="https://github.com/kysgattu/Pedestrain-Detection-System/assets/42197976/aa10d33c-d507-4185-a20a-b716902849dc">


> ### Region Of Interest Selector <a name = 'roi'></a>

Once the Detection button is run, For each Region of Interest a Matplot with a frame from the video pops up on which four points have to be selected which encloses the detection region.

<img width="1280" alt="Screenshot 2023-11-16 at 7 37 57 PM" src="https://github.com/kysgattu/Pedestrain-Detection-System/assets/42197976/338cb935-27a8-442e-b462-c1c8b79763fd">


> ### YOLO Model <a name = 'yolo'></a>
YOLO, or You Only Look Once, is a popular computer-vision object detection algorithm. The key idea behind YOLO is speed and efficiency. Instead of dividing the image into a grid and running object detection on each grid cell, YOLO divides the image into a grid but performs detection for all objects within the entire image in one forward pass of the neural network. YOLO divides the input image into a grid. Each grid cell is responsible for predicting bounding boxes and class probabilities for the objects contained in that cell. Each grid cell predicts multiple bounding boxes along with confidence scores. These bounding boxes represent the location of potential objects in the image. YOLO also predicts the probability of the presence of different classes within each bounding box. After predicting multiple bounding boxes and class probabilities, YOLO uses non-maximum suppression to eliminate duplicate or low-confidence detections. This helps to provide a cleaner and more accurate set of predictions.

> ### Working of the Detection Code <a name = 'code'></a>

The code initiates by configuring parameters like confidence levels, scaling percentages, and tracking thresholds. The video is processed frame by frame using the OpenCV library, with optional scaling for enhanced performance. Regions of interest (ROIs) are defined within each frame, and the code iterates through these, applying YOLO to identify individuals. Subsequently, a tracking mechanism based on object centers is employed to trace the movement of detected persons across frames. The count of individuals within each ROI is continuously updated, and the annotated frames, showcasing bounding boxes, tracking information, and ROI overlays, are compiled into an output video. The final results, including the number of persons detected and tracked in each ROI, are presented upon completion.


> ### Result - Annotated Video <a name = 'result'> </a>
The Annotated video with the number of persons in each ROI is shown in the video - 

https://github.com/kysgattu/Pedestrain-Detection-System/assets/42197976/9d392884-4b89-49e3-8795-f750e2356f84


## Working Demo of the Tool <a name = 'demo'></a>

##### Step-by-Step Instructions for running the tool

- Browse for the source video and the directory to save the annotated video.
- Specify the number of regions (paths) for detecting passing pedestrians.
- Provide names for each region, separated by commas (ensure the number of names matches the specified regions).
- Hit the "Start Detection" button.
- Press enter after selecting four points in the window displaying a frame from the video. Repeat this process for each region; the selection windows will pop up automatically based on the specified number of regions.
- Once the regions are selected, the detection process starts automatically. Note that the progress bar is visible only on the command line.
- After detection is complete, view the counts of each region in the results box.
- Keep in mind that only one detection can be performed per code execution. If errors occur or mistakes are made during data entry, restart the app.

*_A detailed demo of how the tool can be used is shown in below video:_*

https://github.com/kysgattu/Pedestrain-Detection-System/assets/42197976/395e06fc-b10f-4f5c-80f1-ea486e98991b


## Developers <a name='developers'></a>
* [Vijay_bharadwaj(https://github.com/HeyVijay5)


## References <a name='references'></a>

> - [YOLOv4: Optimal Speed and Accuracy of Object Detection](https://doi.org/10.48550/arXiv.2004.10934)
>  
> - [YOLO: Real-Time Object Detection](https://pjreddie.com/darknet/yolo)
>  
> - [Ultralytics YOLOv8 Docs](https://docs.ultralytics.com)

