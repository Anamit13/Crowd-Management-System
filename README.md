# Crowd-Management-System
The system provides real time dynamic crowd heatmap generation with crowd threshold alert notifications and flow management support. It provides real time incident detection.

Crowd Management System

This system provides real time processing of crowd monitoring using CCTV surveillance and can provide many dynamic functions like:
•	Dynamic Heatmap Generation:
1.	We are reading each frame, running it through YOLO and counting the number of detections.
   
 ![image](https://github.com/user-attachments/assets/90e29750-67ff-4788-8384-2e74db7b6acf)

3.	We are generating heatmap dynamically after every 25 frames by converting stored heatmap points into arrays and creating and plotting a 2D density heatmap.

 ![image](https://github.com/user-attachments/assets/c82af261-917a-40e2-bbb5-b2867aba47c7)

•	Crowd Threshold alerts:
1.	The system automatically generated alerts whenever the crowd density gets increased.
   
 ![image](https://github.com/user-attachments/assets/5de1aad1-de80-41cc-b94a-25346340bd28)

3.	Notification service is also implemented when the crowd density goes severe based on the set threshold. In this prototype the we had used Adafruit.io and IFTTT for notification.

 ![image](https://github.com/user-attachments/assets/69674f41-257e-4260-aaaf-65557240beae)
 ![image](https://github.com/user-attachments/assets/21a17774-17f1-46a9-b725-1dacb1166461)
 ![image](https://github.com/user-attachments/assets/e5cc12f6-44f8-4540-bb32-e7bdaf446ecf)
 ![image](https://github.com/user-attachments/assets/b1f02f0d-a712-4f84-b95e-f498bd545543)
 
            
•	Flow Management support:
1.	The dynamically generated heatmap will give us the insights that when we have to stop the entry point to control the crowd volume.
2.	The heatmap will also tell that the crowd volume is low so we can redirect the crowd there.

 ![image](https://github.com/user-attachments/assets/47b03574-5ad6-4325-880e-1771ef1851a8)



Real-time Incident Detection

Step 1: Preprocess UCF-Crime Dataset

•	Convert videos into frames (if needed)

•	Label suspicious vs normal activities

•	Create bounding boxes (optional, if using custom training)

Step 2: Real-Time YOLO-based Incident Detection

•	Since YOLO model is not trained on incidents like abuse or assault, we have to do it manually.

•	For training of YOLO manually, we have to annotate the image by making the bounding boxes of the suspected regions manually using some third-party tool.

•	After that we have to arrange the video frames in the directory format of YOLO with folders of train and label.

•	Now when the model is trained, we can pass the frames to the model to detect abuse, assault, robbery, etc.

•	Trigger alerts when suspicious activity is detected.

Step 3: Geospatial Mapping

•	Assign each video or camera to a simulated location (x, y) or zone

•	Using tools like folium, geopandas, or simple grid overlays on images

•	Visualize incident heatmaps or zone alerts
Step 4: Predictive Analytics
•	Use past data (incident timestamps, locations, counts)
•	Train a lightweight model (e.g., LSTM, ARIMA, or even regression)
•	Forecast next-hour risk levels per zone

