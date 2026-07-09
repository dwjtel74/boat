# Intelligent Water Environment Monitoring Unmanned Boat

## Project Overview

This project is an intelligent unmanned boat system for water
environment monitoring based on ROS2 autonomous navigation technology.
It is designed for scenarios such as urban rivers, lakes, reservoirs,
industrial wastewater monitoring, and emergency water pollution
response.

The system adopts a dual-layer heterogeneous control architecture:

-   **RDK X5**: High-performance onboard computer running Ubuntu and
    ROS2, responsible for SLAM mapping, autonomous navigation, visual
    perception, and AI-based water quality analysis.
-   **STM32F4**: Real-time embedded controller responsible for motor
    control, sensor acquisition, wireless remote control, and safety
    control.
-   **Cloud Platform**: Provides real-time monitoring, data
    visualization, historical analysis, and abnormal alarm functions.

## System Features

-   Autonomous navigation based on ROS2, Cartographer SLAM, and
    Navigation2.
-   Multi-sensor fusion using LiDAR, camera, GPS, and IMU.
-   Real-time monitoring of water temperature, pH, turbidity, and
    conductivity.
-   AI-based dynamic threshold analysis for abnormal water quality
    detection.
-   Dual communication system: 4G MQTT cloud communication and 2.4GHz
    emergency remote control.
-   Web-based monitoring platform with real-time data visualization.

## System Architecture

                        Cloud Monitoring Platform
                                  |
                           MQTT / WebSocket
                                  |
                              4G Network
                                  |
    +------------------------------------------------+
    |                    RDK X5                     |
    | Ubuntu + ROS2                                 |
    |                                                |
    | SLAM | Navigation2 | YOLO Detection           |
    | AI Water Quality Analysis                     |
    +------------------------------------------------+
                             |
                           UART
                             |
    +------------------------------------------------+
    |                  STM32F4                       |
    | Motor Control | Sensor Acquisition | Remote    |
    | Control                                       |
    +------------------------------------------------+
                             |
                  Motors / Water Sensors

## Hardware Components

  Component       Function
  --------------- ------------------------------------------
  RDK X5          Edge computing and ROS2 processing
  STM32F4         Real-time control
  LiDAR           Mapping and obstacle detection
  Camera          Visual recognition
  GPS/IMU         Positioning and attitude estimation
  Water sensors   Temperature, pH, turbidity, conductivity
  Dual motors     Differential propulsion
  4G module       Cloud communication
  2.4GHz module   Remote control

## Software Architecture

### RDK X5 Software

Environment:

-   Ubuntu 22.04
-   ROS2 Humble

Main ROS2 packages:

  Package                 Function
  ----------------------- --------------------------------
  cartographer_ros        SLAM mapping and localization
  nav2_bringup            Autonomous navigation
  yolov26_ros             Water surface object detection
  water_quality_monitor   AI water quality analysis
  stm32_bridge            Communication with STM32

### STM32 Software

Functions:

-   Differential motor control
-   PWM output
-   Water quality sensor acquisition
-   UART communication
-   2.4GHz remote control

## Performance Specifications

  -----------------------------------------------------------------------
  Item                                Specification
  ----------------------------------- -----------------------------------
  Maximum speed                       ≥1.0 m/s

  Positioning accuracy                ≤3 m

  Water quality parameters            Temperature / pH / Turbidity /
                                      Conductivity

  Communication delay                 ≤5 s

  Battery endurance                   ≥3 hours

  Remote control distance             ≥300 m

  Protection rating                   IP67
  -----------------------------------------------------------------------

## Development Process

1.  Requirement analysis
2.  Hardware selection
3.  Layered software development
4.  System integration
5.  Field testing and optimization

## Application Scenarios

-   Urban river monitoring
-   Lake and reservoir water quality inspection
-   Industrial wastewater monitoring
-   Emergency pollution response
-   Smart water management systems

## Future Improvements

-   Multi-boat cooperative operation
-   Multi-depth water sampling
-   Underwater camera and sonar expansion
-   Cloud-based AI model updates
-   Solar-assisted power supply

## License

This project is intended for educational, research, and competition
demonstration purposes.
