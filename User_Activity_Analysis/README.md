# User Activity Analysis

## Overview
This project aims to identify users who have logged at least one activity within 30 days of their registration date. The output should include the user’s ID, registration date, and a count of the number of activities logged within that 30-day period. Users who did not perform any activity within this period should be excluded from the results.

## Interview Question Details
- **Interview Question Date:** November 2024  
- **Company:** Dropbox  
- **Difficulty Level:** Medium  
- **Question ID:** 10541  
- **Roles Applicable:**
  - Data Engineer
  - Data Scientist
  - BI Analyst
  - Data Analyst
  - ML Engineer
  - Software Engineer
    
# Identify users who have logged at least one activity within 30 days of their registration date.
Your output should include the user’s ID, registration date, and a count of the number of activities logged within that 30-day period.
Do not include users who did not perform any activity within this 30-day period.

## Database Schema

### `user_profiles` Table
Contains information about users who have signed up on the platform.

| `user_id` | `name`  | `email`             | `signup_date` |
|----------|--------|--------------------|--------------|
| 1        | Alice  | alice@example.com  | 2024-06-26   |
| 2        | Bob    | bob@example.com    | 2023-07-29   |
| 3        | Charlie| charlie@example.com| 2022-05-30   |
| 4        | David  | david@example.com  | 2024-01-10   |
| 5        | Eva    | eva@example.com    | 2024-06-22   |
| 6        | Frank  | frank@example.com  | 2024-07-27   |
| 7        | Grace  | grace@example.com  | 2022-11-06   |
| 8        | Hank   | hank@example.com   | 2024-09-16   |
| 9        | Ivy    | ivy@example.com    | 2023-01-31   |
| 10       | Jack   | jack@example.com   | 2024-06-07   |

### `user_activities` Table
Contains records of user activities along with their respective timestamps.

| `user_id` | `activity_type` | `activity_date` |
|----------|----------------|---------------|
| 1        | share          | 2024-07-18    |
| 1        | purchase       | 2024-07-23    |
| 2        | logout         | 2024-01-14    |
| 2        | logout         | 2024-02-26    |
| 2        | share          | 2024-01-16    |
| 2        | share          | 2024-01-18    |
| 2        | share          | 2024-01-24    |
| 3        | logout         | 2024-02-29    |
| 4        | login          | 2024-03-07    |
| 4        | share          | 2024-04-17    |
| 6        | login          | 2024-08-13    |
| 7        | comment        | 2024-02-20    |
| 8        | comment        | 2024-10-02    |
| 8        | login          | 2024-10-08    |
| 10       | login          | 2024-06-29    |

## Expected Output
The output should consist of:
- **`user_id`**: The unique identifier for the user.
- **`signup_date`**: The date when the user registered.
- **`activity_count`**: The number of activities the user performed within 30 days of their signup date.

## Approach
1. **Filter Activities Within 30 Days**: Extract users from the `user_profiles` table and match them with activities from the `user_activities` table that occurred within 30 days from their signup date.
2. **Count Activities**: Count the number of activities each user performed within the 30-day period.
3. **Exclude Inactive Users**: Remove users who did not perform any activity during this period.
4. **Present Results**: Display the `user_id`, `signup_date`, and `activity_count` for each eligible user.

## Assumptions
- Each `user_id` in `user_profiles` is unique.
- A user may perform multiple activities.
- The `signup_date` and `activity_date` fields are in `DATE` format.
- Duplicate `user_id` entries in `user_profiles` are ignored.

## Edge Cases Considered
- Users who signed up but never performed any activities.
- Users with multiple activities within the 30-day window.
- Handling of duplicate user records (if any) in `user_profiles`.

## Conclusion
This analysis helps in understanding user engagement trends within their first month on the platform, which can be useful for improving user retention strategies.

