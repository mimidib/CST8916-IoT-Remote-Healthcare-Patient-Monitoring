# CST8916-IoT-Remote-Healthcare-Patient-Monitoring

| | |
|---|---|
| **Semester** | Winter 2026 |
| **Release Date** | February 16, 2026 |
| **Authors** | Jingjing Duan, Iylas Zazai, Mimi Dib |

---

## Overview
This report analyzes a conceptual remote data and real-time application solution used to monitor healthcare patients using IoT wearable device sensor management, real time data dashboards and alerts. 

Wearable devices send patient health data (heart rate, oxygen level, etc.) to Azure IoT Hub, which securely manages device communication. The data is then processed and stored in the backend. If abnormal values are detected, the system generates alerts.

We can use:
REST for patient/device management
GraphQL for dashboard data queries
WebSockets for real-time updates and alerts

This keeps the design realistic, secure, and clearly shows how all three technologies work together.

Also, since this is healthcare data, we should consider security staff:
For devices management -> Azure IoT Hub
For user (e.g, only doctors can see assigned patients) ->Azure AD
For Encrypted communication ->TLS (HTTPS + WSS)
I think these security considerations might give us some extra points.


**Azure Events Hub**: Fully maanged data ingestion service to directly receive and process millions of events per second. Provides telemetry collection, log aggregation and live analytics pipelines and acts as our front door for the event pipeline between user and our analytics, storage and processing workflows. Uses HTTPS protocol and saves the streaming data automatically to Azure Blob Storage.

**Azure IoT Hub**
Our central message hub for bi-directional communication between IoT applications and wearable devices. Provides device identity management, authentication and security for millions of connected devices and supports device-to-cloud telemetry and cloud-to-device commands. 

**Azure Stream Analytics**: Analyzes our real-time data immediately once generated, allowing us  to monitor patients, update dashboards, analyze trends and act fast to alert when patients vitals are abnormal and require immediate care. Uses SQL-like query language, aggregates events over time periods, combines live streaming data with static reference  data (blob storage in our case) for enrichment and context, built-in machine learning for anomaly detection to recognize abnormal vitals, and guaranteed event processing to ensure data is delivered exactly once, so we have confidence we are monitoring all patients vitals.

**Blob Storage** (raw telemetry archive)



**Doctor's Dashboard webapp**

**Power BI historical analytics** pulls from blob




## REST and GraphQL for Data Requests and Updates
*Explain how both REST and GraphQL could be used to handle the data requests and updates required by the system.*

## WebSockets for Real-time Communication
*Describe how WebSockets could be used to handle real-time communication in your chosen system.*

Server needs to push updates to the user frequently WebSocket
Real-time, bidirectional communication needed WebSocket

## Technology Recommendation and Justification
*Recommend which technology (or combination of technologies) you would choose for your system and justify your recommendation based on your analysis in Sections 1 and 2.*

## System Architecture Diagram
*Create a diagram that illustrates the overall architecture of your system, showing how clients, APIs (REST and/or GraphQL), WebSockets, and backend services connect and interact. You may use any diagramming tool (e.g., draw.io, Lucidchart, Excalidraw, Mermaid) and include the diagram as an image in your report.*


## Contributions

- Jingjing
- Ilyas
- Mimi: Architectural Diagram, WebSockets for Real-time Communication report & corresponding slide sections