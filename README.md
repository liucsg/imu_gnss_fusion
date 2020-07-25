# IMU+GNSS Fusion Localization with EKF

-----

## Requirements

* Ubuntu (16.04 or later)
* ROS (kinetic or later)
  - ROS package: nmea_navsat_driver
* GeographicLib 1.50.1 (cmake 3.18.0 tested)
* c++14 (for using `std::make_unique`)

## Build

```sh
mkdir -p ws_msf/src
cd ws_msf/src
git clone xxx
cd ..
catkin_make -j5 # error happened when using the default cmake 3.5.1, upgrade it
```

## Run

test data: [utbm_robocar_dataset_20180719_noimage.bag](https://lcas.lincoln.ac.uk/owncloud/index.php/s/KfItDFgwwis5Xrk)

```sh
roslaunch imu_gnss_fusion imu_gnss_fusion.launch
rosbag play -s 25 utbm_robocar_dataset_20180719_noimage.bag
```

ROS graph and path on rviz:

<p align="center">
  <img src="imgs/rosgraph.jpg"/>
  <img src="imgs/run_imu_gnss_fusion.jpg"/>
</p>

plot the result path(fusion_gps.csv & fusion_state.csv) on google map:

<p align="center">
  <img src="imgs/google_map.jpg"/>
</p>