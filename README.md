# Robot Interface – ROS2 Project

Projekt umożliwia sterowanie robotem TurtleBot3 na podstawie obrazu z kamery i detekcji markerów ArUco.

## Struktura pakietu

Roboty_Projekt/  
├── launch/interface_launch.py  
├── robot_interface/  
│   ├── camera_publisher.py  
│   ├── aruco_detector.py  
│   ├── image_viewer.py  
│   └── turtle_controller.py  
├── package.xml  
├── setup.py  
└── README.md  

## Wymagania  

Ubuntu 22.04  
ROS2 Humble  
OpenCV: sudo apt install python3-opencv  
cv_bridge: sudo apt install ros-humble-cv-bridge  
TurtleBot3 + Gazebo: sudo apt install ros-humble-turtlebot3 ros-humble-turtlebot3-gazebo  

## Instalacja  

cd ~/ros2_ws/src/  
git clone https://github.com/Reaktyw/Roboty_Projekt

cd ~/ros2_ws  
colcon build  
source install/setup.bash  

Plik launch uruchamia wszyskie nody:  
ros2 launch robot_interface interface_launch.py  

Generator ArUco do sterowania robotem do pokazywania przed kamerą:  
https://chev.me/arucogen/  
Dictionary: 6x6 (50, 100, 250, 1000)  
Marker ID: 42  

## Uruchamianie z robotem TurtleBot3 w Gazebo  
Uruchomienie symulacji:  
export TURTLEBOT3_MODEL=burger  
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py  

Sprawdzanie czy robot się porusza:  
ros2 topic echo /odom  
