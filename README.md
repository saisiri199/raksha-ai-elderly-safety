# raksha-ai-elderly-safety
AI-based privacy-preserving elderly fall detection and caregiver alert system.
# Raksha AI — Privacy-Preserving Elderly Safety Monitoring

## About the Project

Raksha AI is an AI-assisted safety monitoring system designed to help caregivers monitor the well-being of elderly people living alone. It focuses on detecting potential emergencies, particularly falls in the bathroom, and enabling timely alerts to caregivers.

The system aims to balance safety, privacy, and accessibility by using privacy-preserving visual detection in the living room and presence and movement monitoring in the bathroom.

## Problem Statement

Elderly people living alone may experience falls or other emergencies without immediate assistance. Bathrooms are particularly high-risk areas, and delays in identifying emergencies can increase the danger.

Traditional monitoring methods may rely on continuous video surveillance or wearable devices, which can raise privacy concerns or may not always be practical.

Raksha AI aims to address these challenges through privacy-conscious monitoring and an emergency alert workflow.

## Key Features

- **Privacy-Preserving Living Room Monitoring:** Uses pose estimation to represent a person through a skeletal landmark structure rather than displaying identifiable facial details or raw video in the caregiver dashboard.
- **Bathroom Presence Monitoring:** Designed to use the HLK-LD2410C radar module to monitor presence and movement.
- **Potential Fall Detection:** Identifies possible fall situations using the available detection logic.
- **Emergency Verification:** Includes a 20-second verification window to allow the system to check a potential emergency before escalation.
- **Caregiver Dashboard:** Displays monitoring information and safety states, including Normal, Possible Fall, Checking Response, Alert Sent, and Resolved.
- **Emergency Notifications:** Designed to support alerts to caregivers through SMS and WhatsApp, subject to service integration and configuration.
- **Hardware Simulation:** Supports simulated inputs during development when physical hardware is unavailable.

## System Architecture

1. **Input Layer:** Receives camera-based pose information and bathroom presence or movement data.
2. **Detection Layer:** Processes available inputs to identify potential safety concerns.
3. **Decision Layer:** Determines the current safety state and starts the emergency verification workflow when required.
4. **Dashboard Layer:** Presents monitoring states to the caregiver.
5. **Notification Layer:** Initiates configured emergency notifications when escalation conditions are met.

## Technologies Used

- Python
- Computer Vision and Pose Estimation
- MediaPipe
- HTML, CSS, and JavaScript (if used by the dashboard)
- ESP32
- HLK-LD2410C radar module
- Web Serial API (if used for dashboard-to-ESP32 communication)
- SMS and WhatsApp integration (subject to implementation)

## Hardware Requirements

- ESP32 development board
- HLK-LD2410C radar module
- Compatible computer or laptop
- Camera for living-room pose detection
- Required USB cables and connections

Hardware requirements may vary depending on the configuration used for the demonstration.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
```

Replace `YOUR-USERNAME` and `YOUR-REPOSITORY` with the actual GitHub username and repository name.

### 2. Open the Project

```bash
cd YOUR-REPOSITORY
```

### 3. Install Dependencies

Install the dependencies specified by the project. If a `requirements.txt` file is provided for the Python components, run:

```bash
pip install -r requirements.txt
```

### 4. Run the Application

Follow the instructions for the dashboard and detection components provided in their respective folders. Hardware-based features may require connecting and configuring the ESP32 and HLK-LD2410C module.

**Note:** Exact installation and execution commands depend on the final project structure and implemented components.

## Simulation Mode

During development, simulated inputs can be used to demonstrate the monitoring workflow when the physical radar hardware is unavailable.

Example simulation inputs:

- `0` — No person detected
- `1` — Person detected
- `2` — Possible person-on-floor event
- `R` — Reset simulation

These inputs represent the development simulation and should not be interpreted as validated real-world fall detection.

## Privacy and Safety

- The living-room dashboard is designed to prioritize skeletal pose representation over identifiable video display.
- Camera processing and data handling should follow appropriate privacy and consent practices.
- The system is a prototype and is not a substitute for professional medical care, emergency services, or a validated safety monitoring device.
- Detection accuracy and emergency notification reliability must be evaluated before any real-world deployment.

## Current Development Status

Raksha AI is a hackathon prototype. Features may be at different stages of development, including simulation, integration, and hardware testing.

The implemented status of each feature should be verified against the code included in this repository.

## Future Enhancements

- Improve potential fall detection and reduce false alarms.
- Complete and test radar hardware integration.
- Strengthen caregiver notification reliability.
- Expand testing under different environmental conditions.
- Improve deployment, documentation, and accessibility.

## Team

Developed collaboratively by the Raksha AI hackathon team.

## License

Add an appropriate license before publicly distributing or reusing this project's source code.
