# 🍀 Schedule Plotter - College Schedule Maker

A comprehensive web-based schedule management system designed specifically for college students, with special attention to the needs of irregular students navigating complex academic paths.

## 🌞 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Demo](#demo)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the App](#running-the-app)
- [Project Structure](#project-structure)
- [Usage Guide](#usage-guide)
- [Development Roadmap](#development-roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Acknowledgments](#acknowledgments)

## 🌞 Overview

**Schedule Plotter** is a React-based web application that allows college students to manually create, manage, and visualize their class schedules. Unlike traditional scheduling tools, this system is built with the flexibility needed by irregular students who must navigate prerequisite chains, varying credit loads, and non-linear academic paths.

### Why Schedule Plotter?

- **Visual Planning**: See your entire week at a glance with an intuitive grid interface
- **Conflict Detection**: Automatically detects scheduling conflicts and overlapping classes
- **Flexible Scheduling**: Support for classes from 7:30 AM to 9:30 PM, Monday through Sunday
- **Multi-Semester Management**: Plan multiple semesters and compare different schedule scenarios
- **Export & Share**: Export your schedule as an image for easy sharing and printing
- **No Database Required**: All data stored locally in your browser - complete privacy

## 🌞 Features

### Core Scheduling Features 
- [x] Drag-and-drop interface for adding classes to time slots
- [x] Multiple schedule templates (weekly, bi-weekly, custom patterns)
- [x] Semester/term-based organization with archiving
- [x] Block scheduling support (consecutive classes, lab + lecture pairing)
- [x] Alternative schedule generation (create "Plan A, B, C" scenarios)
- [x] Conflict detection and prevention (overlapping classes, time conflicts)
- [x] Free time slot highlighting between classes
- [x] Schedule comparison view (side-by-side schedule options)

### Class Information Management
- [x] Course code, title, section input
- [x] Professor/instructor name
- [x] Room/building/campus location
- [x] Class type indicators (lecture, lab, online, hybrid)
- [x] Credit units tracking
- [x] Class color coding and categorization
- [x] Prerequisites and co-requisites tracking
- [x] Class notes/memo field

### Visual Design & User Experience
- [x] Modern, clean, minimalist aesthetic
- [x] Dark mode / Light mode toggle
- [x] Customizable color themes
- [x] Mobile-responsive design (works on phones, tablets)
- [x] Grid-based weekly calendar view
- [x] List view option
- [x] Monthly calendar overview
- [x] Daily agenda view

### Mobile & Accessibility
- [x] Progressive Web App (PWA) support
- [x] Offline access to schedules
- [x] Widget support (today's schedule on home screen)
- [x] Quick add class shortcut
- [x] Screen reader compatibility
- [x] Keyboard navigation support
- [x] High contrast mode
- [x] Adjustable font sizes

### Data Management & Security
- [x] Browser localStorage for data persistence
- [x] Automatic backup
- [x] Data export (PDF, Excel, CSV, JSON)
- [x] Schedule printing (printer-friendly format)
- [x] Import from previous semesters
- [x] Privacy-first design (no server, no tracking)
      

## 🌞 Tech Stack

### Frontend
- **React** 18.2+ - UI library
- **React Hooks** - State management (useState, useReducer, useContext)
- **Tailwind CSS** 3.4+ - Utility-first CSS framework

### Utilities & Tools
- **react-icons** - Icon library
- **html2canvas** - Export schedule as PNG/JPG
- **uuid** - Generate unique IDs for classes and semesters

### Development Tools
- **Vite** / **Create React App** - Build tool
- **ESLint** - Code linting
- **Prettier** - Code formatting
- **Git** - Version control
- **GitHub** - Code hosting and collaboration

### Browser APIs
- **localStorage** - Client-side data persistence
- **Service Workers** - PWA offline support (future)

## 🌞 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v14.0 or higher)
- **npm** (v6.0 or higher) or **yarn** (v1.22 or higher)
- **Git** (for version control)

Check your versions:
```bash
node --version
npm --version
git --version
```

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR-USERNAME/schedule-plotter.git
   cd schedule-plotter
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```
   
   Or if you prefer yarn:
   ```bash
   yarn install
   ```

3. **Verify Tailwind CSS setup**
   
   Ensure these files exist:
   - `tailwind.config.js`
   - `postcss.config.js`
   - Tailwind directives in `src/index.css`

### Running the App

**Development Mode:**
```bash
npm start
```

The app will open at `http://localhost:3000` (or your configured port).

**Production Build:**
```bash
npm run build
```

The optimized production build will be in the `build/` folder.

**Preview Production Build:**
```bash
npm run preview
```

## 🌞 Project Structure

```
schedule-plotter/
├── node_modules/          # Dependencies (not committed)
├── public/                # Static files
│   ├── index.html        # HTML template
│   ├── manifest.json     # PWA manifest
│   └── robots.txt        # SEO
├── src/                  # Source code
│   ├── components/       # React components
│   │   ├── Schedule/     # Schedule grid components
│   │   │   ├── ScheduleGrid.jsx
│   │   │   ├── TimeColumn.jsx
│   │   │   ├── DayColumn.jsx
│   │   │   └── ClassBlock.jsx
│   │   ├── ClassModal/   # Add/Edit class modal
│   │   │   ├── ClassModal.jsx
│   │   │   ├── ClassForm.jsx
│   │   │   └── FormFields.jsx
│   │   ├── Sidebar/      # Navigation sidebar
│   │   │   ├── Sidebar.jsx
│   │   │   ├── SemesterSelector.jsx
│   │   │   └── ViewToggle.jsx
│   │   └── common/       # Reusable components
│   │       ├── Button.jsx
│   │       ├── Modal.jsx
│   │       ├── Input.jsx
│   │       └── Dropdown.jsx
│   ├── hooks/            # Custom React hooks
│   │   ├── useLocalStorage.js
│   │   ├── useSemester.js
│   │   └── useSchedule.js
│   ├── utils/            # Utility functions
│   │   ├── timeUtils.js
│   │   ├── conflictDetector.js
│   │   ├── exportUtils.js
│   │   └── storageKeys.js
│   ├── constants/        # Configuration constants
│   │   └── scheduleConfig.js
│   ├── App.jsx           # Main app component
│   ├── index.js          # Entry point
│   └── index.css         # Global styles (Tailwind)
├── .gitignore            # Git ignore rules
├── package.json          # Dependencies and scripts
├── postcss.config.js     # PostCSS configuration
├── tailwind.config.js    # Tailwind CSS configuration
└── README.md             # This file
```

### Key Files Explained

#### `src/constants/scheduleConfig.js`
Contains all configuration constants:
- Time slots (7:30 AM - 9:30 PM)
- Days of the week
- Class types (lecture, lab, online, hybrid)
- Default color palette
- localStorage keys

#### `src/hooks/useLocalStorage.js`
Custom hook for persistent data storage in browser localStorage.

#### `src/utils/timeUtils.js`
Utility functions for time manipulation:
- Convert 24hr to 12hr format
- Check time overlaps
- Calculate time differences

#### `src/utils/conflictDetector.js`
Algorithm to detect scheduling conflicts between classes.

## 🌞 Usage Guide

### Creating Your First Schedule

1. **Create a Semester**
   - Click "Create New Semester" button
   - Enter semester name (e.g., "1st Semester 2024-2025")
   - Click "Save"

2. **Add a Class**
   - Click the "Add Class" button (top-right)
   - Fill in class details:
     - Course Code (required)
     - Class Title (required)
     - Professor name
     - Room/Building
     - Select days (check Mon-Sun)
     - Choose start and end time
     - Pick a color
   - Click "Save"

3. **View Your Schedule**
   - Class appears as a colored block on the grid
   - Shows course code and room number
   - Spans across selected days and time range

4. **Edit a Class**
   - Click on any class block
   - Modal opens with pre-filled data
   - Make changes and click "Save"

5. **Delete a Class**
   - Click on the class block to edit
   - Click "Delete" button at bottom
   - Confirm deletion

### Managing Multiple Semesters

- Use the semester dropdown to switch between semesters
- Each semester maintains its own set of classes
- Archive old semesters for reference
- Create alternative schedules (Plan A, B, C)

### Conflict Detection

- System automatically detects overlapping classes
- Warning appears when saving conflicting class
- Conflicting classes highlighted in red
- Option to override or cancel

### Exporting Your Schedule

1. **Export as Image**
   - Click "Export" button
   - Choose PNG or JPG format
   - Schedule downloads as image file

2. **Print Schedule**
   - Click "Print" button
   - Print-friendly layout opens
   - Use browser print dialog

3. **Export Data**
   - Click "Export Data" button
   - Downloads JSON file with all schedule data
   - Can import later to restore

### Customization

**Color Themes:**
- Click color picker when adding/editing class
- Each class can have unique color
- Group similar classes with same color

**Display Options:**
- Toggle 12hr/24hr time format
- Show/hide weekends
- Switch between views (weekly, daily, list)
- Enable dark mode

## 🌞 Development Roadmap

### Phase 1: Core Foundation ✅ (Current)
- [x] Project setup
- [x] Folder structure
- [x] Configuration files
- [x] Utility functions
- [x] GitHub repository

### Phase 2: Schedule Grid  (In Progress)
- [ ] Time column component
- [ ] Day columns component
- [ ] Grid layout
- [ ] Responsive design

### Phase 3: Class Management
- [ ] Add class button
- [ ] Add/Edit class modal
- [ ] Form validation
- [ ] Save to localStorage
- [ ] Display classes on grid

### Phase 4: CRUD Operations
- [ ] Edit class functionality
- [ ] Delete class functionality
- [ ] Duplicate class
- [ ] Drag-and-drop (optional)

### Phase 5: Conflict Detection
- [ ] Overlap checking algorithm
- [ ] Visual conflict indicators
- [ ] Warning modals
- [ ] Resolution suggestions

### Phase 6: Semester Management
- [ ] Create semester
- [ ] Switch semesters
- [ ] Delete semester
- [ ] Archive semesters

### Phase 7: Visual Enhancements
- [ ] Dark mode
- [ ] Custom themes
- [ ] Animations
- [ ] Improved mobile UI

### Phase 8: Alternative Views
- [ ] Daily view
- [ ] List view
- [ ] Monthly overview
- [ ] Comparison view

### Phase 9: Export & Print
- [ ] Export as PNG/JPG
- [ ] Print layout
- [ ] PDF export (optional)
- [ ] Share functionality

### Phase 10: Advanced Features
- [ ] Schedule templates
- [ ] Free time visualization
- [ ] Travel time calculator
- [ ] Settings panel
- [ ] PWA optimization

### Future Considerations
- [ ] Backend integration (optional)
- [ ] User authentication
- [ ] Cloud sync
- [ ] Collaboration features
- [ ] University system integration
- [ ] Mobile native apps


**Project Link:** (https://github.com/sewadotwav/schedule-plotter)

## 🌞 Acknowledgments

### Inspiration
- Inspired by the challenges faced by irregular college students
- Built to address the gap in flexible scheduling tools for non-traditional academic paths

### Technologies & Libraries
- [React](https://reactjs.org/) - The amazing UI library
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [react-icons](https://react-icons.github.io/react-icons/) - Beautiful icon library
- [html2canvas](https://html2canvas.hertzen.com/) - Screenshot functionality
- [uuid](https://github.com/uuidjs/uuid) - Unique ID generation

### Resources
- [React Documentation](https://reactjs.org/docs/getting-started.html)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [MDN Web Docs](https://developer.mozilla.org/)
- [Stack Overflow Community](https://stackoverflow.com/)


## 🐞 For Students

This tool was built **by students, for students**. We understand:
- The struggle of finding the right class combinations
- The complexity of prerequisite chains
- The need for flexible scheduling
- The importance of visualizing your academic path


---

## 🌞 Quick Start (TL;DR)

```bash
# Clone
git clone https://github.com/yourusername/schedule-plotter.git

# Install
cd schedule-plotter
npm install

# Run
npm start

# Build
npm run build
```

---

<div align="center">

**Made with love for college students everywhere (⁠≧⁠▽⁠≦⁠)**

</div>

---

**Last Updated:** November 29, 2024  
**Version:** 0.1.0 (Alpha)  
**Status:** 🚧 In Active Development
