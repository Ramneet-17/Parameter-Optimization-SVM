# Parameter-Optimisation-SVM


**Dataset Used:** [Covertype Data Set](http://archive.ics.uci.edu/ml/datasets/covertype)
**Dataset Description**
|Name                                     |Data Type|    Measurement |                      Description|
|-----------------------------------------|---------|----------------|----------------------------------|
|Elevation                               |quantitative   | meters                       |Elevation in meters|
|Aspect                                  |quantitative   | azimuth                      |Aspect in degrees azimuth|
|Slope                                   |quantitative   | degrees                      |Slope in degrees|
|Horizontal_Distance_To_Hydrology        |quantitative   | meters                       |Horz Dist to nearest surface water features|
|Vertical_Distance_To_Hydrology          |quantitative   | meters                       |Vert Dist to nearest surface water features|
|Horizontal_Distance_To_Roadways         |quantitative   | meters                       |Horz Dist to nearest roadway|
|Hillshade_9am                           |quantitative   | 0 to 255 index               |Hillshade index at 9am, summer solstice|
|Hillshade_Noon                          |quantitative   | 0 to 255 index               |Hillshade index at noon, summer soltice|
|Hillshade_3pm                           |quantitative   | 0 to 255 index               |Hillshade index at 3pm, summer solstice|
|Horizontal_Distance_To_Fire_Points      |quantitative   | meters                       |Horz Dist to nearest wildfire ignition points|
|Wilderness_Area (4 binary columns)      |qualitative    | 0 (absence) or 1 (presence)  |Wilderness area designation|
|Soil_Type (40 binary columns)           |qualitative    | 0 (absence) or 1 (presence)  |Soil Type designation|
|Cover_Type (7 types)                    |integer        | 1 to 7                       |Forest Cover Type designation|

**Data Preprocessing**
Dropped the soil type and dropped 3 Types from the Cover Types
As the data didnt containany null values no need for filling null values
The data is been Standard Scaler

| Number of Instances:  |8896  |
|-----------------------|--------|
| Number of Attributes: | 15     |

---
**Parameter Grid Used**
---
|Hyperparameter         |Values                |
|-----------------------|----------------------|
| kernel                | 'linear', 'poly', 'rbf', 'sigmoid' |
| C                     | 0.001, 0.01, 0.1, 1, 10    |
| gamma                 |['scale', 'auto'] + list(np.logspace(-3, 3, 7))   |
| max iter              | 500,1000|

---
 
 | Sample Number | Best Accuracy | Kernel | C  | gamma |
|----------|---------------|--------|-----|-------|
| 1        | 0.817159985013113       | rbf    | 1.000 | 1.000   |
| 2        | 0.81566129636568        |  rbf    | 1.000 | 1.000   |
| 3        | 0.809291869614087       | rbf    | 1.000 | 1.000   |
| 4        | 0.807043836642937       | rbf    | 10.000 | 1.000   |
| 5        | 0.807043836642937       | rbf    | 10.000 | 1.000   |
| 6        | 0.806669164481079        | rbf    | 10.000 | 1.000  |
| 7        | 0.800299737729486        | rbf    | 1.000 | 1.000   |
| 8        | 0.799925065567628       | rbf    | 1.000 | 1.000   |
| 9        | 0.794304983139752        | rbf    | 10.000 | 0.1   |
| 10       | 0.793180966654177       | rbf    | 10.000 | 1.000 |

---

**Sample 1 gives the Best SVM accuracy with params: Kernel=rbf ,C=1.000 and Gamma=1.000**

---

Graph of Accuracy where max iteration ranegs from 1 to 1000 for Sample 1 is:

![alt text](https://github.com/Ramneet-17/Parameter-Optimization-SVM/blob/main/iter%20vs%20acc.png)
