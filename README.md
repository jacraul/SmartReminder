
# SmartReminder

**Developed by:** Tudor-Neculai Bâlbă & Raul-Anton Jac  
**Group:** 1231EA  

---

## Introduction

**SmartReminder** is an Android application designed to help users manage tasks efficiently. With SmartReminder, users can:

- Add tasks with specific deadlines.
- Receive timely notifications 24 hours, 1 hour, and at the exact moment before the task deadline.
- Share daily schedules via social apps.
- Stay updated with weather forecasts and motivational quotes.

---

## Features

- **Task Notifications:** Alerts 24 hours, 1 hour, and at the task’s deadline.
- **Weather Updates:** Real-time weather information displayed in the notification bar.
- **Daily Quotes:** Inspirational quotes fetched from ZenQuotes API.
- **Dark Mode:** Theme switching between light and dark modes.
- **Share Functionality:** Share daily task schedules with others.
- **Persistent Storage:** SQLite database for task management.

---

## Technologies Used

- **IDE:** Android Studio
- **Language:** Kotlin
- **Database:** SQLite
- **APIs:**
  - [ZenQuotes API](https://zenquotes.io/api/random)
  - [OpenWeather API](https://openweathermap.org/api)

---

## File Structure

### Main Directories:
- **app**
  - **manifests**
    - `AndroidManifest.xml`
  - **java/kotlin**
    - `com.example.smartreminder`
      - `AboutActivity.kt`
      - `AddTask.kt`
      - `Database.kt`
      - `DeadlineNotifier.kt`
      - `DeadlineReceiver.kt`
      - `MainActivity.kt`
      - `TasksActivity.kt`
      - `SettingsActivity.kt`
      - `WeatherService.kt`
  - **res**
    - **drawable**: App icons and images
    - **layout**: XML files for UI layouts
    - **values**: XML files for themes and constants

---

## Key Components and Explanations

### Database (Database.kt)

- SQLite database stores tasks with the following schema:
  - **ID**: Unique task identifier.
  - **TASK**: Task description.
  - **DEADLINE_DATE**: Task deadline date.
  - **DEADLINE_TIME**: Task deadline time.
- Key Functions:
  - `addTask`: Adds a new task.
  - `deleteTask`: Deletes a specific task.
  - `getAllTasks`: Fetches all tasks.
  - `getTodayTasks`: Retrieves tasks scheduled for the current day.

### MainActivity

- **APIs:**
  - **Quotes API**: Fetches motivational quotes via a GET request.
  - **Weather API**: Fetches current weather information.
- **Notifications:**
  - Handles alerts 24 hours, 1 hour, and at task deadlines.
  - Processes task date and time to schedule accurate notifications.
- **Task Management:**
  - Displays today’s tasks or a "No tasks today" message.
- **Share Functionality:**
  - Allows sharing the daily schedule through social apps.

### TasksActivity

- **Task Operations:**
  - View, add, and delete tasks.
- **User Interaction:**
  - Long press to prompt task deletion confirmation.

### AddTask

- Allows users to select a task deadline (date and time) with validation.
- Prevents incomplete task entries before adding to the database.

### SettingsActivity

- **Theme Management:**
  - Implements light and dark mode switching.
- **Weather Service Control:**
  - Starts or stops the weather notification service.

### WeatherService

- Continuously fetches and displays real-time weather updates.
- Runs as a foreground service to ensure reliability.
- Updates the notification bar every 60 seconds.

### DeadlineNotifier & DeadlineReceiver

- **DeadlineNotifier:**
  - Schedules alarms for task notifications.
- **DeadlineReceiver:**
  - Listens for alarms and triggers notifications.

---

## Usage of Android Components

- **Foreground Services:** Weather updates in the notification bar.
- **Background Services:** Task notifications.
- **Intents:** Navigation and data sharing.
- **Activities:** Separate screens for task management, settings, etc.
- **Broadcast Receivers:** Handle scheduled alarms.
- **Shared Preferences:** Save user preferences for themes.
- **Content Providers:** Enable sharing daily schedules.
- **Database:** Manage task data with SQLite.
- **External APIs:** Fetch quotes and weather data.
- **Notifications:** Alerts at multiple time intervals.

---

## Future Enhancements

- Add customizable notification intervals.
- Support multiple languages.
- Integrate with cloud services for task synchronization.

---

## Contributors

- Tudor-Neculai Bâlbă
- Raul-Anton Jac

---

## License

This project is licensed under the [MIT License](LICENSE).
