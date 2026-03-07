# Campus Multi-Room Reservation System

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Tkinter](https://img.shields.io/badge/GUI-Tkinter-green.svg)](https://docs.python.org/3/library/tkinter.html)
[![License](https://img.shields.io/badge/License-Academic-orange.svg)](LICENSE)

> A polished Tkinter GUI application for university students to reserve campus facilities: Study Rooms (自習室), Discussion Rooms (討論室), and Sports Rooms (運動室).

**Course:** COMP2090SEF / COMP8090SEF / COMP S209W - Object-Oriented Programming  
**Institution:** Hong Kong Metropolitan University (HKMU)  
**Semester:** 2026 Spring  
**Instructors:** Dr. Jimmy S. Ren & Dr. Patrick Chan

---

## Table of Contents

- [Features](#features)
- [Demo Video](#demo-video)
- [Technologies](#technologies)
- [Installation](#installation)
- [Usage Guide](#usage-guide)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)
- [Future Improvements](#future-improvements)
- [Acknowledgments](#acknowledgments)
- [License](#license)

---

## Features

**Core Functionality:**
- **Three Room Types:** Study Rooms, Discussion Rooms, and Sports Rooms with type-specific rules
- **User Authentication:** Secure 8-digit student ID login with validation
- **Room Search:** Filter by room type, date, time range, and capacity
- **Reservation Management:** Book, view, and cancel reservations with confirmation dialogs
- **Conflict Detection:** Automatic prevention of double-booking and time overlaps
- **In-Memory Storage:** Fast, lightweight data management without external databases

**GUI Highlights:**
- Polished Tkinter interface using `ttk` styled widgets
- Login window with input validation and error messageboxes
- Intuitive main menu with clear navigation
- Treeview displays for rooms and reservations
- Form validation with user-friendly error messages
- Date/Time format: `YYYY-MM-DD HH:MM`

---

## Demo Video

**[Watch 5-Minute Introduction Video](https://www.youtube.com/your-video-link-here)**

*The video demonstrates: login flow, room search, making a reservation, viewing bookings, and cancellation.*

---

## Technologies

| Technology | Purpose | External Install |
|------------|---------|------------------|
| **Python 3.8+** | Core programming language | Pre-installed |
| **Tkinter** | GUI framework | Standard library |
| **ttk** | Styled widgets (from tkinter) | Standard library |
| **datetime** | Time slot management | Standard library |
| **abc** | Abstract Base Classes | Standard library |
| **typing** | Type hints | Standard library |

**No pip install required!** This project uses only Python standard libraries.

---

## Installation

### Prerequisites
- Python 3.8 or higher installed on your system

### Setup Steps

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/campus-room-reservation.git
   cd campus-room-reservation
   ```

2. **Verify Python version:**
   ```bash
   python --version
   # Should show Python 3.8 or higher
   ```

3. **No additional packages needed!** All dependencies are part of Python's standard library.

---

## Usage Guide

### Running the Application

```bash
# Navigate to the project directory
cd campus-room-reservation

# Run the main application
python main.py
```

### Step-by-Step User Guide

#### 1. Login
- Launch the application
- Enter an **8-digit Student ID** (e.g., `12345678`, `87654321`)
- Sample IDs pre-loaded: `12345678`, `87654321`, `11111111`, `22222222`, `33333333`
- Invalid inputs (letters, wrong length) will show error messageboxes and prompt again

#### 2. Main Menu
After successful login, choose from:
- **Search Available Rooms** - Find rooms by type, date, time, and capacity
- **Make a Reservation** - Book a room with date/time selection
- **View My Bookings** - List all your active reservations
- **Cancel Reservation** - Cancel an existing booking
- **Logout** - Return to login screen

#### 3. Making a Reservation
1. Select room type (Study/Discussion/Sports)
2. Enter date (`YYYY-MM-DD`) and time (`HH:MM`)
3. Specify group size
4. Click "Find Available Rooms"
5. Select a room from the list
6. Click "Confirm Reservation"

#### 4. Room-Specific Rules
| Room Type | Min People | Max People | Special Rules |
|-----------|------------|------------|---------------|
| Study Room | 1 | 4 | Quiet environment, whiteboard optional |
| Discussion Room | 2 | 8 | AV equipment available |
| Sports Room | 1 | 20 | Equipment check required, 15-min buffer |

---

## Project Structure

```
campus-room-reservation/
|
├── main.py              # Entry point & GUI implementation
├── models.py            # Data models (Room classes, User, Reservation, TimeSlot)
├── manager.py           # Business logic & reservation management
├── utils.py             # Validation utilities & helper functions
├── README.md            # This file
└── LICENSE              # License information
```

### File Descriptions

| File | Purpose |
|------|---------|
| `models.py` | Defines all data classes: AbstractRoom, StudyRoom, DiscussionRoom, SportsRoom, User, Reservation, TimeSlot |
| `manager.py` | Central controller ReservationManager handling search, booking, cancellation, and sample data initialization |
| `utils.py` | Helper classes ValidationUtils, DateTimeUtils, FormatUtils for input validation and formatting |
| `main.py` | GUI implementation with LoginWindow, MainWindow, SearchRoomsWindow, MakeReservationWindow, ViewBookingsWindow, CancelReservationWindow |

---

## Screenshots

*Add your screenshots to a `screenshots/` folder and update the paths below*

### Login Screen
![Login Screen](screenshots/login.png)
*8-digit student ID validation with error handling*

### Main Menu
![Main Menu](screenshots/main_menu.png)
*Clean navigation with 5 main functions*

### Room Search
![Room Search](screenshots/search.png)
*Filter by type, date, time, and capacity with Treeview results*

### My Bookings
![My Bookings](screenshots/bookings.png)
*Treeview display of all active reservations*

---

## Future Improvements

### Current Limitations
1. **In-Memory Storage** - Data is lost when application closes
2. **No Admin Panel** - Cannot add/remove rooms at runtime
3. **Single User Sessions** - No multi-user concurrency handling
4. **No Notifications** - No email/SMS reminders for bookings

### Potential Enhancements
- SQLite database for persistent storage
- Admin interface for room management
- Email notification system for reminders
- Recurring reservation support
- Mobile-responsive web interface
- QR code check-in system
- Real-time availability updates

---

## Acknowledgments

- **Dr. Jimmy S. Ren** - Course instructor and OOP methodology guidance
- **Dr. Patrick Chan** - Project supervision and feedback
- **Hong Kong Metropolitan University** - Providing the learning platform
- **Python Software Foundation** - Excellent documentation for tkinter and datetime

### References
- [Python Official Documentation](https://docs.python.org/3/)
- [Tkinter Documentation](https://docs.python.org/3/library/tkinter.html)
- [ABC Abstract Base Classes](https://docs.python.org/3/library/abc.html)

---

## License

This project is licensed for **Academic Use Only**.

```
Copyright (c) 2026 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software for academic, educational, and non-commercial purposes only,
subject to the following conditions:

1. The above copyright notice and this permission notice shall be included
   in all copies or substantial portions of the Software.
2. Commercial use is prohibited without prior written permission.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND.
```

---

## Links

- **GitHub Repository:** [https://github.com/yourusername/campus-room-reservation](https://github.com/yourusername/campus-room-reservation)
- **Demo Video:** [YouTube - 5 Min Introduction](https://www.youtube.com/your-video-link-here)
- **Issue Tracker:** [GitHub Issues](https://github.com/yourusername/campus-room-reservation/issues)

---

<p align="center">
  <b>Built for HKMU COMP2090SEF / COMP8090SEF</b><br>
  <i>Spring 2026</i>
</p>
