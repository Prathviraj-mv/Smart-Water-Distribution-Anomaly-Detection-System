# Smart Water Distribution & Anomaly Detection
A multi-node IoT system for real-time monitoring and analysis of water distribution networks, designed using a zone-based modular architecture. Each zone operates as an independent monitoring unit with a complete sensing stack, enabling scalable deployment across geographically distributed pipelines and storage systems.

Each zone includes:

Main sensing unit: flow sensor, BMP180 (pressure + temperature), TDS, and pH for water quality and flow monitoring
Valve monitoring unit: MPU6050 IMU mounted on valves to capture vibration patterns indicating leaks, stress, or disturbances
Tank monitoring unit: ultrasonic sensor for water level measurement, with solar-assisted power for remote operation

All sensor nodes stream data continuously via serial communication, handled using PySerial. A central processing system built with Flask (Python) ingests this data in real time. Incoming data is structured into zone-wise dictionaries, enabling clean separation of multiple zones, synchronized comparison, and efficient state tracking across the network.

The system implements a hybrid anomaly detection pipeline:

A Random Forest model, trained on a synthetic dataset, performs multi-parameter classification. It considers correlations between flow, pressure, vibration, and water quality to identify complex patterns such as combined leak + contamination scenarios.
Rule-based logic is layered on top for deterministic validation and fast triggering. These include:
Pressure drop correlated with flow inconsistency
Sudden spikes or irregular patterns in vibration data
Abrupt deviation in TDS and pH values indicating contamination
Tank level inconsistencies relative to inflow/outflow conditions

The frontend is implemented using HTML and CSS, providing a lightweight and responsive web dashboard. It includes:

Live streaming of sensor values
Zone-wise panels for independent monitoring
Status indicators (normal/abnormal states)
Real-time anomaly alerts
Basic visualization for trend observation

The zone-based dictionary structure in the backend allows direct mapping between physical nodes and logical monitoring units, simplifying debugging, scaling, and future integration with control systems.

This architecture emphasizes:

Modularity: each zone is self-contained and replicable
Scalability: additional zones can be added without redesign
Fault isolation: issues can be localized to specific zones or components
Reliability: multi-sensor fusion reduces false positives compared to single-sensor systems

By correlating multiple sensing modalities within each zone and comparing behavior across zones, the system enables accurate detection of leaks, blockages, contamination, and structural issues in pipelines. It provides a practical, deployable solution for continuous monitoring of water distribution infrastructure in both urban and semi-remote environments.
# Project Gallery

## Hardware

<table>
  <tr>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.24.jpeg" width="100%"/></td>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.25.jpeg" width="100%"/></td>
  </tr>
  <!-- <tr>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.25 (1).jpeg" width="100%"/></td>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.26.jpeg" width="100%"/></td>
  </tr> -->
  <tr>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.27.jpeg" width="100%"/></td>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.27 (1).jpeg" width="100%"/></td>
  </tr>
  <tr>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.28.jpeg" width="100%"/></td>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.44.jpeg" width="100%"/></td>
    
  </tr>
  <tr>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.41.jpeg" width="100%"/></td>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.42.jpeg" width="100%"/></td>
  </tr>
  <tr>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.43.jpeg" width="100%"/></td>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 10.43.34.jpeg" width="100%"/></td>
  </tr>
</table>


## Software Dashboard

<table>
  <tr>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 09.29.53.jpeg" width="100%"/></td>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 09.29.53 (1).jpeg" width="100%"/></td>
  </tr>
  <tr>
    <td><img src="Images/WhatsApp Image 2026-05-02 at 09.31.04.jpeg" width="100%"/></td>
    <td></td>
  </tr>
</table>

## CAD Design

<table>
  <tr>
    <td><img src="Images/Screenshot 2026-04-27 194228.png" width="100%"/></td>
    <td><img src="Images/Screenshot 2026-04-27 194642.png" width="100%"/></td>
  </tr>
</table>
