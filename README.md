[![Typing SVG](https://readme-typing-svg.demolab.com?font=Poppins&size=18&pause=1000&color=F7B21E&random=false&width=435&lines=Football+Player+Detection+and+Tracking+%F0%9F%8F%88)](https://git.io/typing-svg)

Football automated analytics ⚽ is hot topics in the intersection between AI and sports. In this project, we build a tool for detecting and tracking football players, referees and ball in videos. For this we use [YOLOv5](https://github.com/ultralytics/yolov5) (the latest version of the popular and fast object detector) for detecting the players in each frame of the video, and [ByteTrack](https://github.com/ifzhang/ByteTrack) a multi object detection model released in 2022 to identify the players and track their trajectory.

For the data, we use videos from the [DFL - Bundesliga Data Shootout](https://www.kaggle.com/competitions/dfl-bundesliga-data-shootout/data) competition on Kaggle for the demo. For training YOLOv5, we use the [football-players-detection](https://universe.roboflow.com/roboflow-jvuqo/football-players-detection-3zvbc) dataset from Roboflow.

You can also use our dataset [football-players-detection-custom](https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking/blob/main/Dataset/football-players-detection.v4i.yolov5pytorch.zip).

## Table of content <!-- omit from toc -->
- [YOLOv5](https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking?tab=readme-ov-file#yolov5)
- [ByteTrack](https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking?tab=readme-ov-file#bytetrack)
- [Screenshots](https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking?tab=readme-ov-file#-screenshots)
- [Technology Stack](https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking?tab=readme-ov-file#technologies-used-%EF%B8%8F)
- [Project Structure](https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking?tab=readme-ov-file#project-structure)
- [Contributors](https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking/blob/main/README.md#contributors)
- [License](https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking?tab=readme-ov-file#license)
- [Conclusion](https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking?tab=readme-ov-file#conclusion)



## YOLOv5 

YOLOv5 is a state-of-the-art object detection model developed by Ultralytics, known for its exceptional performance, accuracy, and efficiency. It utilizes advanced deep learning techniques and a unique model architecture, combining convolutional neural networks and transformer-based attention mechanisms to accurately detect and localize objects in real-time. One of its key strengths is the ability to strike a balance between speed and accuracy, processing multiple frames per second while maintaining high precision. YOLOv5 is highly versatile, capable of being trained on a wide range of datasets, including custom datasets tailored to specific use cases, making it a valuable tool for researchers, developers, and companies working in various domains. With its impressive performance, efficient inference, and user-friendly interface, YOLOv5 has become a popular choice among the computer vision community.

## ByteTrack

ByteTrack is a Multi Object Tracker, it identifies the detected objects and tracks their trajectory in the video. The algorithm uses tracklets, representation of tracked objects, to store the identity of detections.

The main idea of BYTE (the algorithm behind ByteTrack), is to consider both high and low confidence detections.For each frame the position of the bounding boxes are predicted using a Kalman filter from thprevious positions. The high confidence detections are matched with these predicted tracklets by iou and are identified.The low confidence detection are compared with unmatched tracklets (identified objects are not associated to any bounding box in that frame). This helps identity occulted objects.A bin of unmatched tracklets is kept for **_n_** frames to handle object rebirth. They are deleted beyond **_n_** if they remain unmatched.

## 👨‍💻: Screenshots

### ● Output Result
<div align="left">
 
| Football Player Detection | Football PLayer Tracking | 
| :---         |     :---      |       
| <img src="https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking/blob/main/Result/Football_Detection_Result.jpg" width="500" height="auto" />  | <img src="https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking/blob/main/Result/Football_player_tracking.png" width="500" height="auto" />    
| _Note : Check results folder for tracking video_ |

</div>

### ● Parametric Result
<div align="left">

| Results (Graph) |
| :---         |   
 <img src="https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking/blob/main/Result/Parametric%20Results/results.png" width="auto" height="auto" />   | 

| Results |
| :---         |   
 <img src="https://github.com/Shrey2dew/Football-Player-Detection-and-Tracking/blob/main/Result/Parametric%20Results/Results(text).png" width="auto" height="auto" />   | 

</div>

## Technologies Used ⚙️
1. Ultralytics YOLOv5m (Model)
2. ByteTrack (Video Tracking)
3. Roboflow Supervision (Video Processing)

## Project Structure
```
├─── Dataset/
├─── Detection and Tracking Files/
│     └─── Football_Player_Detection(Upload_from_Comp).ipynb
│     └─── football_player_tracking.ipynb
├─── Results/
│     └─── Football_Tracking_Result.mp4
│     └─── Parametric Results
├─── Weights/
│     └─── best.pt
├─── Runtime change.gif/
├─── README.md
├─── Project Report Sem VI.pdf
├─── LICENSE
└─── .gitignore
```

## Contributors

1. [Shrey Nalode](https://github.com/Shrey2dew)
2. [Yash Prabhat](https://github.com/yashhh-03)
3. [Rishi Maheshwari](https://github.com/rishi899)

## License

Distributed under the MIT License. See [License](https://choosealicense.com/licenses/mit/) for more information.

Please adhere to this project's `code of conduct`.

## Conclusion
In conclusion, this project leverages the power of Ultralytics YOLO models and ByteTracking
for detection and tracking of football players , football , referee and goalkeeper which help football associations to carefully monitor and analyse each and every player.
