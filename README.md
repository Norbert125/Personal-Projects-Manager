# Personal Projects Manager

A simple, offline personal project tracker built with .NET MAUI for **Windows** and **Android**.

Break each project into steps, break each step into todos, tick them off, and see how far along you are.

> **Status:** in development.

## Features

- **Projects** with a name, description, status (Idea / Active / Paused / Done), priority, and due date
- **Steps** inside each project, each with notes
- **Todos** inside each step, each with an optional due date
- **Progress tracking**: completed todos roll up into a per-step count and a per-project progress bar
- **Drag & drop** to reorder steps and todos, or move a todo to another step
- **Overview tab**: overdue items, active projects, and stats at a glance
- **Safe deletes**: deleting a project needs a confirmation plus typing `Delete <project name>`
- **Fully offline**: all data lives in a local SQLite database on your device
- Light and dark theme

## Tech stack

| | |
|---|---|
| Framework | .NET 10 (LTS), .NET MAUI |
| UI | XAML, MVVM ([CommunityToolkit.Mvvm](https://www.nuget.org/packages/CommunityToolkit.Mvvm)) |
| Storage | SQLite via [sqlite-net-pcl](https://www.nuget.org/packages/sqlite-net-pcl); each project is stored as one row with its steps and todos as JSON |
| Platforms | Windows 10/11, Android |

## Getting started

### Requirements

- Visual Studio 2026 with the **.NET Multi-platform App UI development** workload
- .NET 10 SDK
- For Android: an emulator (Android Device Manager in Visual Studio) or a physical device with USB debugging enabled

### Run

1. Clone the repository.
2. Open `Personal Projects Manager/Personal Projects Manager.slnx` in Visual Studio.
3. Pick a target in the toolbar: **Windows Machine**, or an Android emulator/device.
4. Press **F5**.

## Project structure

```
Personal Projects Manager/
├── Models/        Project, Step, Todo, and progress calculation
├── Services/      Database (SQLite access)
├── ViewModels/    one per page
├── Views/         XAML pages
└── Resources/     styles, colors, icons, fonts
```

## Data

The database file `projects.db3` is stored in the app's private data folder. Uninstalling the app (especially on Android) deletes all data. There is no backup or export yet.
