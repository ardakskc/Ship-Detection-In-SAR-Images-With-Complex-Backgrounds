# Ship-Detection-In-SAR-Images-With-Complex-Backgrounds
Ship Detection In SAR Images With  Complex Backgrounds project including codes, report docs and article.

Synthetic aperture radar (SAR) is one of the most important active imaging systems in remote sensing. Since SAR is not affected by clouds, day and night, it gives the best images that can be used in ship detection. 

In this project, the structure of the SAR dataset, which was obtained from Sentinel-1 and Gaofen-3 satellites and composed of approximately 40,000 images, was tried to be explained. Deep learning algorithms fitting for ship detection from the dataset have been decided.

First, different versions of the YOLO algorithm (v3Tiny, v4, v5) were used for ship detection. Then these algorithms were compared among themselves in terms of speed and performance using certain parameters like average precision (AP), average recall (AR) and detection time. SSD-MobileNet, EfficientDet D0 and Faster R-CNN algorithms were added to these comparisons and the most suitable algorithm for ship detection was tried to be found.


Project Results:


![Ekran görüntüsü 2022-10-01 141518](https://user-images.githubusercontent.com/44347054/193406914-56734930-7847-461d-9519-a378ca32e623.png)


Detection Results:



![Ekran görüntüsü 2022-10-01 142015](https://user-images.githubusercontent.com/44347054/193407083-12c4c70e-fd20-4867-a451-958a048e0259.png)


The metrics used for performance analysis were obtained with the object detection tool, which makes these metric calculations much easier. 
As seen from results, some complex images were picked to show some examples. As expected Yolov3Tiny shows least promise. EfficientDet, SSD-MobileNet and Faster R-CNN
predicted some ships that don’t exist. It can be said that Yolov5 is better at ship detection in complex backgrounds. It can be seen from Table 3 that Yolov5 performs best as it seems from mAP metric. Even though Yolov4 is the fastest, it is decided that Yolov5 should be used for the comparison with the rest of the methods. It should be noted that, even though the hyperparameters that was used in this paper were not equal, it does not mean that it was not a fair study. We firmly believe that the working environment should be a critera as well. 


EfficientDet D0 and Faster R-CNN were tried to train with the same batch size as SSD-MobileNet v2 but it was pushing the working environment much harder than expected. The batch size was lowered in this study because of this problem. The batch sizes that were given were actually the biggest batch sizes that could given.
Table shows that the most successfull method was YOLOv5 based on the most popular metric, mAP. EfficientDet-D0 was pretty close, but it was detecting ships a little bit faster. The biggest difference makers in these two methods were APL and ARL metrics which show the ability to detect the larger ships. YOLOv5 is actually much better at detecting large ships. The other difference maker metric is AP75 which shows us the AP metric calculated for IoU values greater than 0.75. This means YOLO draws ship boundries better than EfficientDet. The fastest method in this study is SSD-MobileNet V2, fitting the purpose of design. SSD-MobileNet v2 detects two times faster than its closest competitor. Another point that worth noting is that Faster R-CNN performs poorly in comparison. It’s much more slower than the other methods, and has really low success rate at detecting large ships as it can be seen from APL and ARL metrics. We think the reason for that because of the low
batch size, it was not trained as well as the other methods.




Project Contributors:

-Arda Kaşıkçı

-Ömer Batuhan Özbay
