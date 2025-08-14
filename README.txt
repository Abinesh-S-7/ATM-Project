# Face Detection and Alert System

## Project Overview
This project implements a comprehensive face detection and alert system designed for security monitoring. The system combines face recognition, mask detection, and crowd monitoring capabilities with real-time SMS alerts using Twilio.

## Detailed System Components

### 1. Face Recognition System
- Utilizes training images stored in `TrainingImage/` directory
- Supports multiple user profiles with individual directories
- Real-time face detection and matching
- Stores unknown face captures for review

### 2. User Management System
- User details stored in `Details/Details.csv`
- Stores comprehensive user information:
  - User ID
  - Full Name
  - Phone Number
  - Initial Deposit
- Supports multiple user profiles

### 3. Alert System (sms1.py)
- Real-time SMS notifications via Twilio
- Alert triggers for:
  - No mask detection
  - Multiple people detection (>2 people)
  - Unknown face detection
- Image attachment capability for visual verification

## Project Structure
```
├── Unknown_Face_Captures/    # Stores images of unrecognized faces
├── TrainingImage/           # Contains user face training data
│   ├── 000/                # Individual user directories
│   ├── 123/
│   └── [other user IDs]/
├── TrainingImageLabel/      # Stores labeled training images
├── uploads/                 # Temporary storage for captured images
├── Details/                 # User information storage
│   └── Details.csv         # User database
├── new/                     # New user registration/updates
├── sms1.py                  # SMS alert functionality
└── last_otp.txt            # OTP storage
```

## Features
- Advanced face detection and recognition
- Real-time mask detection
- Crowd monitoring (detects more than 2 people)
- Instant SMS alerts via Twilio
- Image capture and storage
- Training image management
- User profile management
- OTP-based verification
- Unknown face logging

## Prerequisites
- Python 3.x
- Twilio account and credentials
- Required Python packages:
  - twilio
  - opencv-python
  - numpy
  - face_recognition

## Setup Instructions
1. Clone this repository
2. Install required dependencies:
   ```
   pip install twilio opencv-python numpy face_recognition
   ```
3. Configure Twilio credentials in `sms1.py`:
   - Replace `TWILIO_ACCOUNT_SID`
   - Replace `TWILIO_AUTH_TOKEN`
   - Replace `TWILIO_PHONE_NUMBER`
   - Replace `TO_PHONE_NUMBER`
4. Update the `IMAGE_SERVER_URL` in `sms1.py` with your server URL

## Usage
1. Place training images in the `TrainingImage` directory
2. Configure user details in `Details/Details.csv`
3. Run the face detection system
4. The system will:
   - Monitor for faces
   - Check for masks
   - Monitor crowd size
   - Send SMS alerts when conditions are triggered

## Alert Conditions
- No mask detected
- More than 2 people detected in the area
- Unknown face detected

## Data Management
- User data stored in CSV format
- Images organized in separate directories
- Separate storage for unknown faces
- Temporary storage for uploads
- Regular cleanup required

## Security Notes
- Keep your Twilio credentials secure
- Regularly update the training images
- Monitor the system logs for any suspicious activities
- Protect user data and privacy
- Regular security audits recommended

## Maintenance
- Regularly clean up the `Unknown_Face_Captures` directory
- Update training images as needed
- Monitor Twilio account usage and limits
- Regular system health checks
- Backup user data regularly

## Integration Points
- Twilio API for SMS
- Image server for storing and serving captured images
- Face recognition system
- User management system

## Support
For any issues or questions, please create an issue in the repository.

## License
[Specify your license here]

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request. 