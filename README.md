# Objective
To facilitate LiDAR .laz formatted data by running an arcpy script to create a high resolution 0.5 Digital Eleveation Model (DEM).

## About the data presented
Data presented in this project was collected in Lone Oaks Farm. Lone Oaks Farm is owned by the University of Tennessee Institute of Agriculture and administered by UT Extension.  It is a world-class venue for education, business retreats, special events, and family travel. One stream ran straight through the farm until West Tennessee River Basin Authority (WTRBA) funded by Ford restored the stream to enhance its ecological services.

![Alt Text](/lone1.png)

The data was collected with an airborne LiDAR sensor and was used to propose a project to the WTRBA. The data will be used to assess the effectiveness of restoration measures taken at Lone Oaks.

## Flowchart

![Alt Text](/flowchart.png)

## Original dataset
<iframe width="800" height="600" frameborder="0" scrolling="no" allowfullscreen src="https://arcg.is/y5rab"></iframe>
# Classifying the ground

## Main focus of the script - Classifying the ground
```python
#classify Ground
arcpy.ddd.ClassifyLasGround(
    in_las_dataset = las_dataset,
    method = "CONSERVATIVE", #method to classify ground to non-ground points
    dem_resolution = 5, #resolution for sampling
    reuse_ground="RECLASSIFY_GROUND",
    dem_resolution="0.5 Meters",
    compute_stats="COMPUTE_STATS",
    extent="DEFAULT",
    boundary=None,
    process_entire_files="PROCESS_EXTENT",
    update_pyramid="UPDATE_PYRAMID",
    algorithm="LATEST",
    classify_low_noise="NO_CLASSIFY_LOW_NOISE",
    minimum_depth_below_ground="0.25 Meters",
    preserve_low_noise="RECLASSIFY_LOW_NOISE",
    classify_high_noise="NO_CLASSIFY_HIGH_NOISE",
    minimum_height_above_ground="100 Meters",
    preserve_high_noise="RECLASSIFY_HIGH_NOISE"
)
```


---



