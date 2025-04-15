# STOP_WATCH

### 1. **Importing Libraries:**
   - **`Tkinter`:** The built-in Python library used for creating the graphical user interface (GUI) of the stopwatch.
   - **`datetime`:** Used to manage and format the time displayed on the stopwatch.

### 2. **Global Variables:**
   - **`counter`:** A global variable that keeps track of the elapsed time in seconds.
   - **`running`:** A global boolean variable used to track whether the stopwatch is running or stopped.

### 3. **Function: `counter_label(label)`**
   - **Purpose:** This function is responsible for continuously updating the stopwatch display.
   - **Working:**
     - If the stopwatch is running, the counter increments every second.
     - If the counter is 0 (initial state), it shows "Ready!".
     - If the stopwatch is running, it converts the counter value (in seconds) into a readable time format (HH:MM:SS).
     - It uses `label.after(1000, count)` to call the function every 1000 milliseconds (1 second) to update the display.
   
### 4. **Function: `Start(label)`**
   - **Purpose:** Starts the stopwatch when the "Start" button is clicked.
   - **Working:**
     - Sets the `running` variable to `True` to indicate the stopwatch is running.
     - Calls the `counter_label` function to update the display.
     - Disables the "Start" button (`state = 'disabled'`).
     - Enables the "Stop" and "Reset" buttons (`state = 'normal'`).

### 5. **Function: `Stop()`**
   - **Purpose:** Stops the stopwatch when the "Stop" button is clicked.
   - **Working:**
     - Sets the `running` variable to `False` to stop the stopwatch.
     - Disables the "Stop" button (`state = 'disabled'`).
     - Enables the "Start" and "Reset" buttons (`state = 'normal'`).

### 6. **Function: `Reset(label)`**
   - **Purpose:** Resets the stopwatch to 00:00:00 when the "Reset" button is clicked.
   - **Working:**
     - If the stopwatch is not running (i.e., the "Stop" button was clicked), it resets the `counter` to 0 and updates the display to "00:00:00".
     - If the stopwatch is running, it immediately resets the display to "00:00:00" but the stopwatch will continue running.

### 7. **GUI Setup:**
   - **Main Window (`root`):** 
     - The window is created using `Tkinter.Tk()`, with the title "Stopwatch".
     - The window size is set to a minimum of 250x70 pixels using `root.minsize()`.
   - **Display (`label`):** 
     - A label is created to display the current time, initially set to 'Ready!' with a font size of 30 and bold style.
     - This label will update with the time as the stopwatch runs.
   - **Frame (`f`):**
     - A frame (`Tkinter.Frame`) is used to hold the buttons for the stopwatch (Start, Stop, Reset).
   - **Buttons:**
     - **Start Button:** 
       - Initially enabled, and when clicked, it calls the `Start()` function to begin the stopwatch.
     - **Stop Button:**
       - Initially disabled. When the stopwatch is running, clicking it will stop the stopwatch by calling the `Stop()` function.
     - **Reset Button:**
       - Initially disabled. When the stopwatch is stopped, clicking it will reset the stopwatch to 00:00:00 using the `Reset()` function.

### 8. **Button Placement:**
   - The "Start", "Stop", and "Reset" buttons are placed within the frame `f` and packed side by side using `side='left'`.
   - The frame is centered using `f.pack(anchor='center', pady=5)`.

### 9. **Main Loop:**
   - The GUI runs in an infinite loop (`root.mainloop()`) that listens for user input and updates the interface accordingly (clicking buttons, etc.).

### Summary:
- **Purpose of the Program:** This is a simple stopwatch application that allows the user to start, stop, and reset a timer.
- **Key Features:**
  - **Start:** Starts the stopwatch and continuously updates the time every second.
  - **Stop:** Stops the stopwatch and disables the stop button.
  - **Reset:** Resets the stopwatch to 00:00:00, either when running or stopped.
- **Buttons:**
  - Start: Starts the stopwatch.
  - Stop: Stops the stopwatch.
  - Reset: Resets the time to 00:00:00.
- The GUI layout is managed with Tkinter, and the program updates every second using the `after()` method to repeatedly call the counter function.
