# Average Session Duration Analysis

## Overview
This repository contains a solution to a StrataScratch SQL/Python task that calculates the average session duration (in seconds) for each session type using the `twitch_sessions` dataset.

## Task Description
Given a dataset containing Twitch session data, the objective is to compute the average session duration for each session type (`streamer` and `viewer`). The dataset includes:
- `user_id`: Unique identifier for users.
- `session_start`: Timestamp marking the beginning of the session.
- `session_end`: Timestamp marking the end of the session.
- `session_id`: Unique identifier for each session.
- `session_type`: Indicates whether the user is a `streamer` or a `viewer`.

## Solution Approach
The solution is implemented in Python using the Pandas library and follows these steps:
1. Load the dataset into a Pandas DataFrame.
2. Convert `session_start` and `session_end` columns into datetime format.
3. Calculate the session duration by subtracting `session_start` from `session_end`.
4. Compute the average session duration per `session_type`.
5. Display the results.

## Files in this Repository
- `solution.py`: Contains the Python code to solve the task.
- `README.md`: This document explaining the task and solution approach.

## Usage
To run the solution, execute the `solution.py` script in a Python environment with Pandas installed.
```bash
python solution.py
```

## Dependencies
Ensure you have Python 3 and Pandas installed:
```bash
pip install pandas
```

## Expected Output
The script outputs the average session duration (in seconds) for each session type, formatted as a DataFrame.

## License
This project is open-source and free to use.

