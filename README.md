NeuroBotic’s: Autonomous Robotics Project for WRO Future Engineers Guatemala 2025
________________________________________
Introduction
In the rapidly evolving field of robotics, the ability to design and develop autonomous systems that can perform complex tasks without 
human intervention is of paramount importance. The World Robot Olympiad (WRO) is a prestigious international competition that encourages 
students worldwide to showcase their skills in robotics and programming. Our team, NeuroBotic’s, is proud to represent Guatemala in the 
2025 WRO Future Engineers category. This document provides a comprehensive overview of our project, detailing our mission, vision, 
objectives, design, development process, challenges, and future aspirations.
________________________________________
Mission

Our mission is to develop innovative autonomous robotic solutions that can be integrated into various practical applications, including 
agriculture, environmental protection, and home automation. We aim to create robots that not only optimize everyday tasks but also 
promote sustainability, efficiency, and social wellbeing. Through this project, we are committed to fostering interest in STEM (Science, 
Technology, Engineering, and Mathematics) among young people and demonstrating the potential of Guatemalan engineering talent on an 
international stage.
________________________________________
Vision
We envision a future where autonomous robotic systems are seamlessly incorporated into daily life to enhance productivity and improve 
quality of life. NeuroBotic’s aspires to be a leading robotics team in Latin America, recognized for its innovation, ethical commitment, 
and technical excellence. By participating in competitions like WRO, we strive to expand our knowledge, push technological boundaries, 
and inspire others to pursue careers in robotics and automation.
________________________________________
Project Objectives
1.	Design and construct an autonomous robot capable of navigating a complex course that includes obstacles, corners, and color-coded
2.	signals.
3.	Integrate multiple sensors, such as ultrasonic distance sensors and a Pixy2 CMUcam5 smart camera, to enable real-time decision-making.
4.	Develop modular, efficient software using C++ and Arduino IDE to control the robot’s motors, sensors, and navigation logic.
5.	Adhere strictly to WRO regulations, including the use of only one DC motor for propulsion and one servo motor for steering.
6.	Document the engineering process thoroughly, including hardware schematics, software architecture, testing results, and lessons
7.	learned.
8.	Promote teamwork and innovation, fostering a collaborative environment where all members contribute ideas and efforts.
9.	Represent Guatemala proudly at national and international robotics events.
________________________________________
Team Structure
Our team consists of highly motivated students with complementary skills:
•	Team Leader: Coordinates the project timeline, documentation, and overall strategy.
•	Lead Programmer: Develops and refines the codebase, ensuring reliability and efficiency.
•	Hardware Specialist: Designs and assembles the mechanical and electrical components.
•	Testing and Quality Assurance: Conducts rigorous tests to validate system performance.
Regular meetings and open communication ensure that all members stay aligned and contribute effectively throughout the project.
________________________________________
Hardware Components
Our robot’s hardware setup was carefully selected to meet the competition’s requirements while maximizing performance:
•	Microcontroller: ELEGOO Arduino UNO R3 board, serving as the main controller.
•	Motor: A 12V DC motor rated at 10,000 RPM powers the rear wheels, providing adequate torque and speed.
•	Servo Motor: One standard servo controls the steering mechanism by turning the front wheels.
•	Ultrasonic Sensors: Four HC-SR04 sensors placed at strategic positions (front, left, right, and corner) for obstacle detection and 
distance measurement.
•	Vision Sensor: The Pixy2 CMUcam5 camera module provides color-based object recognition to inform navigation decisions.
•	Power Supply: A rechargeable 7.4V ELEGOO lithium battery pack powers the system.
•	Chassis: A lightweight but sturdy frame designed to maintain stability and support all components securely.
•	Wheels: Four rubber wheels with good traction, two driven by the motor and two steering via the servo.
All components were integrated to ensure seamless communication and efficient power distribution.
________________________________________
Software Architecture
The robot’s software is written in C++ using the Arduino IDE and is organized modularly:
•	MotorControl Module: Manages PWM signals to the DC motor for speed regulation and direction control.
•	ServoControl Module: Controls the servo angle for precise steering adjustments.
•	UltrasonicSensor Module: Reads distance data from the HC-SR04 sensors and filters noise.
•	CameraModule: Interfaces with the Pixy2 camera via SPI/I2C to obtain real-time color detection data.
•	Navigation Logic: Implements decision-making algorithms based on sensor input to navigate the course autonomously.
•	State Machine: Defines robot states such as moving forward, turning, stopping, reversing, and scanning, to coordinate behavior.
This modular approach facilitates debugging, code reuse, and future enhancements.
________________________________________
Navigation and Control Logic
The robot employs a combination of sensor data and programmed logic to navigate:
•	The ultrasonic sensors continuously monitor distances to nearby obstacles.
•	When an object is detected within a preset threshold (20 cm), the robot stops and initiates a scanning routine.
•	Using the servo to rotate the front ultrasonic sensor, it measures space available on the right and left.
•	Based on these readings, the robot decides the direction with the most clearance and steers accordingly.
•	If no direction is clear, the robot reverses a small distance and repeats the scanning.
•	The Pixy2 camera detects colored markers along the track to signal specific actions, such as slowing down or turning.
•	PWM signals regulate the speed smoothly to prevent sudden movements that could cause instability.
________________________________________
Mechanical Design
Our chassis was designed with:
•	Compact dimensions to fit within the constraints of the competition track.
•	Stable wheelbase to prevent tipping during sharp turns.
•	Modular mounting points for easy replacement or repositioning of components.
•	Robust construction using high-quality materials to withstand repeated testing.
CAD software was used to create precise blueprints, and 3D-printed parts were utilized for sensor mounts and brackets.
________________________________________
Development Timeline
•	April 2025: Project inception and research on WRO guidelines.
•	May 2025: Component procurement and preliminary chassis assembly.
•	June 2025: Initial motor and sensor integration; programming of basic movement.
•	July 2025: Advanced navigation logic development; Pixy2 integration.
•	August 2025: Extensive field testing; optimization and debugging.
•	August 30, 2025: National WRO competition in Guatemala City.
________________________________________
Challenges Faced
•	Sensor Noise: Ultrasonic readings occasionally fluctuated; solved by implementing averaging filters and timeout checks.
•	Servo Calibration: Initial servo limits caused mechanical strain; adjusted software limits and improved mounts.
•	Power Stability: Battery voltage dips affected performance; added voltage regulators and capacitors.
•	Communication Issues: SPI and I2C bus conflicts managed by careful timing and error handling.
•	Mechanical Alignment: Chassis misalignments fixed by iterative adjustments and custom 3D-printed holders.
Software Implementation Details
Our software architecture is built with modularity and efficiency in mind. Each hardware component is abstracted into a class that 
handles low-level interfacing and data processing. This approach allows us to isolate issues easily and add new features without 
disrupting the overall system.
Motor Control Module
The motor is controlled via PWM signals generated by the Arduino’s timers. Speed regulation is achieved by adjusting the duty cycle, 
while direction control is managed using an H-bridge driver integrated into the SmartCar Shield.
The module supports:
•	Start/Stop commands with smooth acceleration/deceleration curves.
•	Direction switching for forward and reverse motion.
•	Speed adjustment in response to obstacle proximity and track conditions.
Servo Control Module
The steering servo operates within a calibrated angular range (typically 45° to 135°). We implemented functions for:
•	Straight steering at 90° (neutral position).
•	Left and right turns with smooth interpolation to avoid jerks.
•	Dynamic steering adjustments based on sensor inputs during navigation.
Ultrasonic Sensor Module
The four HC-SR04 sensors provide distance measurements at regular intervals. To reduce noise and false triggers:
•	We average multiple readings.
•	Use timeouts to discard out-of-range values.
•	Cross-check front and side sensors to validate obstacle detection.
This sensor fusion improves navigation reliability.
Camera Integration Module
The Pixy2 camera communicates over SPI with the Arduino UNO. We implemented:
•	Initialization routines to start the camera.
•	Functions to read detected color blocks.
•	A mapping system linking detected colors to navigation commands (e.g., red = stop, green = proceed, yellow = caution).
Using Pixy2’s onboard processing allows the Arduino to focus on control rather than image processing.
________________________________________
Autonomous Behavior Algorithm
The core logic follows a state machine paradigm with states such as:
•	Moving Forward: Default state, moves at moderate speed while continuously scanning.
•	Obstacle Detected: Stops and scans right and left directions.
•	Turning: Chooses a direction based on sensor data and steers accordingly.
•	Reversing: If no free path, backs up a fixed distance.
•	Line Color Detected: Modifies speed or behavior depending on color codes.
Transitions between states are triggered by sensor input and timed events, ensuring responsive and predictable robot behavior.
________________________________________
Testing and Calibration
Testing was conducted in progressively more challenging environments:
•	Initial indoor testing on flat surfaces without obstacles to validate basic movement.
•	Controlled obstacle courses with cones and barriers to test ultrasonic detection and avoidance.
•	Simulated competition tracks marked with colored zones to validate Pixy2 detection and color-triggered behaviors.
•	Field testing outdoors to check battery life and mechanical robustness.
Calibration tasks included:
•	Adjusting servo angles for precise turning.
•	Setting ultrasonic sensor thresholds to balance sensitivity and noise immunity.
•	Tuning PWM parameters for smooth motor control.
•	Fine-tuning camera color thresholds for different lighting conditions.
Extensive logging was used to track performance metrics and iteratively improve code.
________________________________________
Power Management
Ensuring reliable power delivery was critical. Our battery pack provides 7.4V nominal voltage, which powers both the motors and the 
electronics through regulated lines. We implemented:
•	Voltage monitoring via Arduino ADC pins.
•	Safe shutdown procedures to prevent damage during low battery.
•	Power filtering to reduce noise affecting sensor readings.
This system guarantees consistent performance during long test sessions and competition runs.
________________________________________
Mechanical Assembly
Special attention was paid to mechanical design to maximize:
•	Durability: Using reinforced brackets and screws to withstand vibrations.
•	Weight distribution: Balanced to improve traction and stability.
•	Ease of maintenance: Components mounted with quick-release fittings to allow rapid adjustments.
The chassis combines aluminum and high-strength plastic parts, with 3D-printed sensor holders that allow flexible positioning.
________________________________________
Safety and Compliance
All electrical wiring is insulated and organized to prevent shorts or interference. The design complies with competition safety 
guidelines, ensuring:
•	No exposed live wires.
•	Secure battery mounting to prevent dislodgement.
•	Emergency stop mechanism accessible via remote button.
Our robot passed preliminary safety inspections without issues.
________________________________________
Collaboration and Workflow
We adopted Agile methodologies, using tools like Trello for task tracking and GitHub for version control. Our workflow included:
•	Sprint planning: Weekly goals set by the team.
•	Daily stand-ups: Brief meetings to review progress and challenges.
•	Code reviews: Peer feedback to maintain code quality.
•	Documentation updates: Regular updates to our engineering notebook and wiki.
This structure improved efficiency and ensured transparency among members.
________________________________________
Ethical Considerations
As future engineers, we recognize our responsibility to develop technology ethically. We:
•	Ensure our code is original and credit all references.
•	Promote fair competition and respect other teams.
•	Advocate for sustainable engineering practices by minimizing waste and reusing components.
•	Raise awareness about robotics ethics and AI safety in our community.
________________________________________
Community Engagement
We shared our progress through social media and school workshops to inspire other students. We organized demos explaining robotics 
basics, fostering interest among younger learners.
________________________________________
Future Development
Plans include:
•	Integrating encoder feedback for improved motion accuracy.
•	Implementing machine learning algorithms for adaptive navigation.
•	Adding wireless telemetry for remote monitoring.
•	Refining mechanical design for better agility.
•	Preparing for international WRO events with enhanced capabilities.
Technical Specifications and Components Overview
The choice of hardware components was driven by balancing performance, reliability, and compliance with WRO rules. Key specifications 
include:
•	Microcontroller: ELEGOO Arduino UNO R3, operating at 16 MHz with 32 KB flash memory, sufficient for managing sensor data and motor 
control.
•	DC Motor: 12V 10,000 RPM motor, providing ample torque to navigate the competition track and obstacles.
•	Servo Motor: Standard 180° servo used for steering, allowing precise control of front wheel direction.
•	Ultrasonic Sensors: Four HC-SR04 sensors with detection range from 2 cm up to 400 cm and accuracy within 3 mm.
•	Pixy2 CMUcam5: Color vision sensor capable of processing up to 50 frames per second, with onboard color blob detection and SPI/I2C 
communication protocols.
•	Battery: 7.4V 2200 mAh Lithium-ion battery pack, supporting extended operation with stable voltage output.
•	Chassis Materials: Aluminum frame for structural rigidity combined with ABS plastic parts for sensor mounts.
All these components were tested for interoperability and power consumption, ensuring the robot meets the competition’s strict hardware 
limitations.
________________________________________
Software Development Environment
Our development environment consisted of:
•	Arduino IDE: Primary platform for coding, compiling, and uploading firmware to the Arduino UNO.
•	GitHub: Version control system to manage code versions, facilitate collaboration, and maintain a changelog.
•	Trello: Project management tool used to track tasks, bugs, and milestones.
•	Serial Monitor: Tool within Arduino IDE used for debugging and real-time sensor data visualization.
•	CAD Software: For mechanical design and 3D printing of custom parts.
________________________________________
Code Structure and Highlights
The codebase is organized into multiple files and modules to enhance readability and maintainability:
•	motor_control.h/cpp: Functions to control motor speed and direction.
•	servo_control.h/cpp: Functions for servo angle setting and calibration.
•	ultrasonic_sensor.h/cpp: Classes for reading distance data and filtering noise.
•	pixy_camera.h/cpp: Interfaces with the Pixy2 camera and processes color data.
•	navigation_logic.ino: Main Arduino sketch implementing the state machine and decision-making.
Key features include interrupt-driven sensor readings for non-blocking operation, PID speed control loops for smooth motion, and event-
driven transitions based on sensor thresholds.
________________________________________
Testing Procedures and Performance Metrics
Extensive testing phases ensured robustness:
•	Unit Testing: Verified each module’s functionality independently.
•	Integration Testing: Ensured hardware and software components worked harmoniously.
•	Stress Testing: Subjected the robot to continuous operation over several hours to check thermal performance and battery endurance.
•	Competition Simulation: Replicated WRO track conditions to measure timing, accuracy, and reliability.
Performance indicators recorded included average speed (0.5 m/s), obstacle detection latency (<100 ms), and successful completion rate of 
obstacle avoidance maneuvers (>95%).
________________________________________
Lessons Learned
Throughout the project, the team gained valuable insights:
•	Importance of modular code design to facilitate troubleshooting.
•	Necessity of proper sensor calibration to avoid false positives.
•	Value of clear documentation to track progress and decisions.
•	Benefits of teamwork and communication in overcoming challenges.
•	The real-world complexity of integrating hardware and software systems.
________________________________________
Future Recommendations
To improve and extend the project, we recommend:
•	Incorporating additional sensors such as gyroscopes and accelerometers.
•	Exploring machine learning techniques for adaptive navigation.
•	Developing a mobile app interface for monitoring and control.
•	Enhancing mechanical design for agility and speed.
•	Participating in workshops and training to deepen robotics knowledge.
________________________________________
Conclusion
The NeuroBotic’s team successfully designed and built an autonomous robot capable of navigating the WRO Future Engineers course with 
precision and reliability. This project exemplifies how innovation, teamwork, and technical skill come together to solve real-world 
problems through robotics. We are proud to represent Guatemala and look forward to continuing our growth as engineers and competitors on 
the international stage.
________________________________________
Acknowledgments
We thank our mentors, teachers, and families for their support and encouragement. Special thanks to the WRO organization for providing a 
platform that inspires young engineers globally. We also appreciate the open-source community and manufacturers whose resources made this 
project possible.
________________________________________
References
•	WRO Official Rules and Guidelines 2025
•	Arduino UNO R3 Datasheet and Documentation
•	Pixy2 CMUcam5 User Manual and SDK
•	HC-SR04 Ultrasonic Sensor Technical Specifications
•	Various online robotics tutorials and forums

