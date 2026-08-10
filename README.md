Computer Vision-Based Livestock Tracking in Pasture Systems
Project Overview
This project develops a low-cost, camera-based framework for high-frequency cattle detection and location tracking in open pasture systems. The goal is to reduce dependence on GPS collars while generating detailed information on cattle presence, distribution, movement, and grazing behavior at approximately one-minute intervals.
The system combines synchronized multi-camera imagery, deep-learning-based cattle detection, image preprocessing, and geospatial calibration. The resulting data are intended to support precision livestock management, grazing research, and improved interpretation of greenhouse gas flux measurements.
Objectives
Build a high-resolution pasture monitoring dataset using multiple cameras collecting daytime images throughout the grazing season.
Develop and evaluate a cattle detection pipeline based on YOLO, a deep-learning model that identifies and locates cattle in images using bounding boxes.
Convert image detections into pasture locations using georeferenced field control points and camera-calibration methods.
Validate image-based results against cattle locations recorded by GPS collars.
Develop a scalable workflow for future duplicate removal across cameras, pasture-wide animal mapping, and automated behavioral monitoring.
Current Workflow
The current pipeline includes:
Multi-camera image acquisition and timestamp synchronization using image metadata.
Manual annotation of cattle in more than 1,200 pasture images.
Training and evaluation of a YOLOv8 Large cattle detector.
Adaptive sky removal using the Segment Anything Model (SAM), a general-purpose image-segmentation model.
Camera-specific masking to exclude areas outside the monitored pasture.
Automated export of annotated images, cattle counts, and bounding-box coordinates.
Alternative approaches, including additional model fine-tuning, tiled-image training, and DINO-based visual feature extraction, were also evaluated. The full-image YOLO pipeline provided the most reliable cattle counts and was retained as the primary detection framework.
Next Steps
Ongoing development will focus on:
Detecting and removing duplicate observations across overlapping camera views.
Converting image coordinates into real-world pasture coordinates.
Comparing camera-derived locations and counts with GPS collar data.
Mapping cattle movement and spatial distribution across the pasture.
Applying the tracking data to grazing-management and greenhouse-gas research.
Study Site and Data
Field data are collected from a summer-grazed pasture at the Eastern Nebraska Research, Extension and Education Center. Cameras collect high-resolution images at one-minute intervals, while GPS collars record reference cattle locations every five minutes. Georeferenced field markers measured with RTK equipment support camera calibration and spatial validation.
Tools and Technologies
Python and PyTorch
Ultralytics YOLO
Segment Anything Model
OpenCV
EXIF metadata processing
R
University of Nebraska Holland Computing Center
Project Team
Principal Investigator: Makki Khorchani, School of Natural Resources, University of Nebraska–Lincoln  
Collaborator: Yijie Xiong, Departments of Animal Science and Biological Systems Engineering, University of Nebraska–Lincoln
Collaborator: Shreyas Kalammanagudi Shankaresh, School of Natural Resources, University of Nebraska–Lincoln
Status
This repository supports an active research project. Code, documentation, and workflows may change as model development, spatial calibration, and GPS-based validation continue.
