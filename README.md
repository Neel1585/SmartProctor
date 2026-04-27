# SmartProctor

## AI Enabled Online Examination & Proctoring System

SmartProctor is a professional web-based online examination platform developed to conduct secure, efficient, and intelligent exams with real-time AI proctoring. It combines exam management, automated result generation, student dashboards, suspicious activity monitoring, and role-based management in one integrated system.

The project is designed to solve major issues of traditional online examinations such as cheating, manual result checking, poor monitoring, and inefficient management.

---

# Project Objective

The main objective of SmartProctor is to build a secure digital examination ecosystem where:

* Students can attend exams remotely.
* Admins can create and manage exams easily.
* AI monitors suspicious behavior during exams.
* Results are generated automatically.
* All records are stored digitally.
* Dashboards provide real-time insights.

---

# Key Features

## Student Module

* Student Registration & Login
* JWT Secure Authentication
* View Live / Upcoming Exams
* Attempt MCQ Based Exams
* Real-Time Countdown Timer
* Auto Submit on Time Completion
* View Results
* Dynamic Student Dashboard
* Profile Management

## Admin Module

* Admin Login
* Create New Exams
* Edit / Delete Exams
* Add Questions with Marks
* Manage Students
* View Student Results
* View Proctoring Logs
* Dashboard Analytics
* Profile Management

## AI Proctoring Features

During the exam, SmartProctor monitors suspicious activities such as:

* No Face Detected
* Multiple Faces Detected
* Tab Switching
* Leaving Seat
* Camera Issues
* Excessive Warnings

All warnings are stored in database logs for review.

---

# Technologies Used

## Frontend

* React.js
* JavaScript
* CSS3
* Vite

## Backend

* Python
* Flask
* Flask CORS
* Flask PyMongo
* JWT Authentication

## Database

* MongoDB

## AI Module

* OpenCV
* Face Detection Logic

---

# Project Structure

```bash
SmartProctor/
│── frontend/
│   ├── src/
│   │   ├── pages/
│   │   ├── components/
│   │   ├── App.jsx
│   │   └── main.jsx
│
│── backend/
│   ├── app.py
│   ├── Login.py
│   ├── Profile.py
│   ├── ExamList.py
│   ├── ExamManagement.py
│   ├── Results.py
│   ├── Proctoring.py
│   ├── StudentManagement.py
│   ├── StudentDashboard.py
│   ├── AdminDashboard.py
│   └── utils.py
```

---

# Database Collections

## USERS

Stores all login accounts.

```text
user_id, name, email, password_hash, role, created_at, last_login
```

## STUDENTS

Stores student-specific details.

```text
student_id, user_id, enrollment_no, department, semester, profile_photo
```

## ADMINS

Stores admin-specific details.

```text
admin_id, user_id, designation, privilege_level
```

## EXAMS

Stores exam details.

```text
exam_id, title, subject, duration_minutes, total_marks, scheduled_at, created_by, status
```

## QUESTIONS

Stores MCQ questions.

```text
question_id, exam_id, question_text, option_a, option_b, option_c, option_d, correct_option, marks
```

## EXAM_ATTEMPTS

Tracks each student attempt.

```text
attempt_id, exam_id, student_id, start_time, end_time, status, ip_address
```

## ANSWERS

Stores submitted answers.

```text
answer_id, attempt_id, question_id, selected_option, is_correct, answered_at
```

## PROCTORING_LOGS

Stores suspicious activities.

```text
log_id, attempt_id, event_type, severity, detected_at, snapshot_url, is_reviewed
```

## RESULTS

Stores final exam results.

```text
result_id, attempt_id, student_id, exam_id, total_score, percentage, grade, generated_at
```

## NOTIFICATIONS

Stores alerts sent to admin.

```text
notif_id, attempt_id, student_id, message, sent_at, is_read
```

---

# Authentication Flow

* User logs in using Email + Password
* JWT Token generated
* Token used for secure protected routes
* Role-based access:

  * Admin
  * Student

---

# Result Generation Logic

After exam submission:

* Correct answers counted
* Marks calculated
* Percentage generated
* Grade assigned:

```text
80+ = A
60+ = B
40+ = C
Below 40 = F
```

---

# API Modules

```text
/api/auth
/api/profile
/api/exam-list
/api/exams
/api/results
/api/proctoring
/api/students
/api/dashboard
/api/student-dashboard
```

---

# Advantages of SmartProctor

* Reduces cheating
* Saves manual checking time
* Instant result generation
* Centralized exam management
* AI based monitoring
* Real-time dashboards
* Remote accessibility

---

# Future Enhancements

* Live screen recording
* AI eye tracking
* Voice detection
* OTP verification
* Subjective question checking
* Certificate generation
* Email notifications
* Mobile Application

---

# Screens Included

* Login Page
* Student Dashboard
* Admin Dashboard
* Exam Interface
* Results Page
* Proctoring Logs
* Profile Page

---

# How To Run Project

## Clone Repository

```bash
git clone <your-github-repository-link>
cd SmartProctor
```

## Backend Setup

```bash
cd backend
pip install flask flask-cors flask-pymongo pyjwt
python app.py
```

Backend runs on:

```text
http://localhost:5000
```

## Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Frontend runs on:

```text
http://localhost:3000
```

---

# Developed By

**Neel Shah**
IT Student
Project Developer – SmartProctor

---

# License

This project is developed for educational and academic purposes.

---

# Final Note

SmartProctor is not just an exam system — it is a smart secure examination ecosystem combining modern web development, databases, automation, and AI monitoring to redefine online examinations.
