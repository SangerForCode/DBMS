# Live DBMS Course Progress Tracker

## Project Aim
This project is a dynamic, single-page web application designed to track progress through a comprehensive Database Management System (DBMS) course. It provides a real-time, shareable dashboard for monitoring completed lectures, key concepts, and mentor feedback.

## Technical Implementation
The application is built as a single `index.html` file, demonstrating a powerful "zero-build" setup. It uses vanilla JavaScript for all logic and leverages Google Firebase (Firestore) for its real-time database backend, enabling live data synchronization across clients. The user interface is styled with Tailwind CSS, loaded via a CDN, and includes features like dynamic progress bars, statistics, and tabbed navigation to create a rich, interactive experience.

## Key Features
- **Real-Time Synchronization:** Uses Firebase to instantly sync lecture progress, concepts, and remarks between users.
- **Dynamic Progress Tracking:** Automatically calculates and visualizes progress against a target schedule, showing if the user is ahead or behind.
- **Interactive Checklist:** Allows users to check off completed lectures and concepts from a predefined list.
- **Built-in Mentorship Tool:** Includes a "Mentor Remarks" tab for providing and tracking timestamped feedback.

## Setup Instructions
- **Prerequisite:** Requires a Google Firebase project with Firestore and Anonymous Authentication enabled.
- **Configuration:** Edit the `index.html` file and replace the placeholder `firebaseConfig` object with your own Firebase project credentials.
- **Run:** Open the `index.html` file in a web browser.

## System Diagram
```mermaid
graph TD
    subgraph "Clients"
        A[User's Browser]
        B[Mentor's Browser]
    end

    subgraph "Frontend"
        C(index.html);
        D{Vanilla JavaScript Logic};
        E{Tailwind CSS (CDN)};
    end

    subgraph "Backend"
        F[(Firebase Firestore)];
    end

    A -- Interacts with --> C;
    B -- Interacts with --> C;

    C -- Contains --> D;
    C -- Styled by --> E;
    
    D -- Reads/Writes Data --> F;
    F -- Real-time Sync --> D;
```
