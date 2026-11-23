# SMART ATTENDANCE TRACKER - WEB APPLICATION
> A modern, responsive, full-featured Student Attendance & Academic Performance Management System.

Built using **HTML5**, **CSS3**, **Vanilla JavaScript (ES6+)**, **LocalStorage**, and **Chart.js**.

---

## 🚀 Live Demo Credentials

| Role | Username | Password | Notes |
| :--- | :--- | :--- | :--- |
| **Administrator** | `admin` | `password123` | Full access: Institutional settings, policy controls, student enrollment, backups |
| **Faculty / Teacher** | `teacher` | `password123` | Classroom marking, student profiles, attendance history, and report generation |

*Convenience feature:* On the login screen, click **"Admin Demo"** or **"Teacher Demo"** for instant 1-click credential autofill.

---

## 📂 Project Architecture

```
attendance-tracker/
├── index.html              # Smart auth router (redirects to dashboard or login)
├── login.html              # Professional login page with validation & demo autofill
├── dashboard.html          # Executive analytics dashboard & KPI statistics
├── students.html           # Full student CRUD, search, multi-filters & modal viewer
├── attendance.html         # Interactive attendance marking board with live tallies
├── history.html            # Daily class records, student logs & monthly calendar
├── analytics.html          # Dynamic charts, threshold calculator & defaulter tracking
├── reports.html            # Report generator with CSV export and print-ready layouts
├── notifications.html      # Center for shortage alerts, absences & system logs
├── settings.html           # Institutional parameters, attendance rules, backup/restore
├── css/
│   ├── style.css           # Complete design system with CSS variables, light/dark mode
│   └── responsive.css      # Adaptations for desktop, tablet, and mobile drawer
├── js/
│   ├── storage.js          # Central LocalStorage data engine, math calculations & seeds
│   ├── auth.js             # Authentication guard, session management & toast alerts
│   ├── dashboard.js        # Dashboard statistics, weekly trend & category charts
│   ├── students.js         # Student registry management, modals & profile viewer
│   ├── attendance.js       # Classroom marking, duplicate prevention & batch actions
│   ├── history.js          # Multi-view historical archives & record editing
│   ├── analytics.js        # Analytics charts, threshold simulator & leaderboard
│   ├── reports.js          # Report engine, CSV file generator & print handler
│   └── settings.js         # Configuration forms, department editor & data reset
└── assets/
    ├── logo.svg            # Vector application shield logo
    ├── logo.png            # Raster PNG application icon
    └── icons/              # Additional application icons
```

---

## 🌟 Key Features & Capabilities

### 1. Executive Dashboard (`dashboard.html`)
- **6 Realtime Metric Cards**: Total Enrolled Students, Today's Present, Today's Absent, Today's Late, Campus Average Attendance %, and Defaulters Count.
- **Weekly Trend Graph (Chart.js)**: 7-day campus attendance rate with smooth curve visualization.
- **Status Breakdown (Chart.js)**: Doughnut chart visualizing Present, Absent, Late, On-Duty (OD), and Leave.
- **Department Comparison (Chart.js)**: Department-wise comparative performance bars.
- **Defaulters Warning Strip**: Instant list of students below 75% attendance with recovery requirements.
- **Recent Submissions Feed**: Realtime log of the latest classroom attendance submissions.

### 2. Student Management (`students.html`)
- **Complete CRUD Operations**: Add, Edit, Delete (with safety checks), and View detailed Student Attendance Profiles.
- **Multi-Filter & Instant Search**: Realtime search by Student Name, Student ID, or Roll Number; filter by Department, Year of Study, and Section.
- **Student Profile Modal**: Displays student metadata, calculated attendance rate, warning status, and chronological attendance log.
- **Duplicate Prevention**: Rejects duplicate Student IDs or Roll Numbers with clear feedback.

### 3. Attendance Marking (`attendance.html`)
- **Classroom Selector**: Filter by Date (with "Today" and "Yesterday" quick buttons), Department, Year, and Section.
- **Duplicate Prevention Notice**: If a session was already marked for that date and class, a warning banner appears detailing who recorded it, allowing seamless updates without accidental duplicates.
- **Visual Status Badges**: High-contrast, tactile status pills for:
  - 🟢 **Present (P)**
  - 🔴 **Absent (A)**
  - 🟡 **Late (L)**
  - 🟣 **On Duty (OD)** (Hackathons, sports, symposiums)
  - 🔵 **Approved Leave (LV)**
- **Batch Controls**: "Mark All Present", "Mark All Absent", and "Reset".
- **Live Summary Tally**: Realtime counter bar tracking Total, Present, Absent, Late, OD, Leave, and Live Attendance Rate %.
- **Per-Student Remarks**: Optional notes field (e.g. "Medical certificate submitted", "Bus breakdown").

### 4. Attendance History & Archives (`history.html`)
- **Triple-View Switcher**:
  1. *Daily Class Records*: Session-level overview with date, class, recorded faculty, status breakdown, and direct "Edit" or "Delete" actions.
  2. *Student-Wise Log*: Granular row-by-row log of every attendance entry for any student.
  3. *Monthly Calendar Grid*: Interactive monthly calendar view displaying attended days, percentages, and session counts.
- **Date Range & Status Filters**: Filter from/to date, department, student name, and attendance status.

### 5. Analytics & Defaulter Calculator (`analytics.html`)
- **Mathematical Formula**:
  $$\text{Attendance \%} = \left(\frac{\text{Effective Present Days}}{\text{Total Working Days}}\right) \times 100$$
- **Configurable Threshold Simulator**: Interactive slider (50% – 95%) dynamically recalculating defaulter counts.
- **Consecutive Recovery Days Calculation**: Automatically calculates how many consecutive working days a student must attend to cross the 75% cutoff:
  $$\text{Required Days } (X) = \left\lceil\frac{\text{Threshold} \times \text{Total Days} - 100 \times \text{Present Days}}{100 - \text{Threshold}}\right\rceil$$
- **4 Interactive Chart.js Graphs**:
  - 14-Day Campus Attendance Curve
  - Attendance Category Distribution Doughnut
  - Department Comparison vs. Threshold (Color-coded: Red below threshold, Blue compliant)
  - Cohort Year-of-Study Comparison
- **Defaulters Shortage Management Table**: Direct action button to generate official shortage notifications.
- **Honor Roll / Leaderboard**: Recognizes top students with 90%+ attendance.

### 6. Reports Section (`reports.html`)
- **6 Report Types**:
  - Overall Consolidated Audit Report
  - Daily Classroom Report
  - Weekly Cumulative Report
  - Monthly Academic Review Report
  - Department-Wise Performance Report
  - Student-Wise Detailed Report
- **Export to CSV**: Client-side generated, RFC-4180 compliant CSV file download with descriptive filename.
- **Print / Save as PDF**: Clean print layout with institutional letterhead, summary stats, clean table styling, and auto-hidden navigation.

### 7. Notification Center (`notifications.html`)
- Automatically populated with alerts for students dropping below threshold, frequent absences, saved attendance logs, and administrative reminders.
- Filter tabs: All, Shortage Warnings, Attendance Saved, and System Info.
- "Mark All as Read" and "Clear All" actions.

### 8. Settings & Policy Management (`settings.html`)
- **Institution Profile**: Change Application Name, College Name, and Academic Year.
- **Attendance Policy Rules**:
  - Toggle whether *On Duty (OD)* counts as Present.
  - Toggle whether *Approved Leave* counts as Attended Days.
  - Late Arrival Rule: *3 Lates = 1 Absent penalty*, *Half Day credit*, or *Full credit*.
- **Department Management**: Add new departments or remove existing ones.
- **Appearance**: Light / Dark mode toggle.
- **Data Persistence & Backups**:
  - *Restore Pre-Seeded Sample Data* (Restores 28 realistic students and 16 days of past attendance sessions).
  - *Export JSON Backup* (Downloads complete LocalStorage state).
  - *Import JSON Backup* (Restores database from file).
  - *Clear All Attendance Logs*.

---

## 💻 How to Run

Because this application uses standard HTML5, CSS3, and modern JavaScript:
1. Open the folder `attendance-tracker/`.
2. Double-click `index.html` or `login.html` to open it in Google Chrome, Microsoft Edge, Firefox, or Safari.
3. No server setup, Node.js installation, or build tools are required!

*(Optional)* You can also serve it with any local static web server such as VS Code's **Live Server** extension.
