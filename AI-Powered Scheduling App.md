Canvas API Token
  
10706~CafnnYz6YPcryUPMyUEXDN4fDvUJhkyMLWCJuPUfxntXrcEwR6hNY9J74HFyUXFM



Prompt for Gemini 3.1 Pro:

> I need you to write a Python script that automates a 3-step academic scheduling workflow. Since I do not have access to the Gemini API keys, the script must function in two distinct phases with a manual copy-paste step in the middle.
> Phase 1: Data Extraction & Prompt Generation
>  * Canvas Integration: Use the Canvas LMS REST API (using a Bearer Token) to fetch my current 'To-Do' list from /api/v1/users/self/todo.
>  * Detail Retrieval: For each assignment found, use the course_id and assignment_id to fetch the full assignment object from /api/v1/courses/{course_id}/assignments/{assignment_id}.
>  * Data Cleaning: Use BeautifulSoup to strip all HTML tags from the assignment description field so it is clean text.
>  * The 'Meta-Prompt': The script should then print a large, well-formatted text block to the console. This block is a prompt meant for ME to copy and paste into Gemini. It should contain:
>    * Clear instructions for Gemini to perform a 'Deep Thinking' task analysis.
>    * The clean text and due dates of all my assignments.
>    * A request for Gemini to return a specific, minified JSON object containing: task_name, estimated_total_hours, and calendar_blocks (an array of suggested  start/end times, with one block per task).
> Phase 2: Manual Input & Calendar Integration
>  * User Input: The script should then use input() to wait for me to paste the JSON response I got back from Gemini.
>  * Google Calendar Integration: Use the Google Calendar API (OAuth2) to parse that JSON and create the actual time blocks on my 'primary' calendar.
> Technical Constraints:
>  * Use requests for Canvas and google-api-python-client / google-auth-oauthlib for Google.
>  * Include error handling for expired Canvas tokens.
>  * Ensure the Google Calendar part handles timezones (e.g., use datetime and pytz).
>  * Provide a clear 'Setup' section in the comments explaining where to put the credentials.json for Google and the CANVAS_TOKEN.


🛠️ How the Resulting Script Will Work
When Gemini 3.1 Pro gives you the code, the workflow will look like this:
| Step | Action | Outcome |
|---|---|---|
| 1 | Run Script | It pulls your Canvas assignments and prints a "Ready-to-Paste" prompt. |
| 2 | Copy/Paste | You paste that block into Gemini 3.1 Pro (with Thinking mode on). |
| 3 | Analyze | Gemini "thinks," breaks down the tasks, and gives you a JSON block. |
| 4 | Paste Back | You paste that JSON back into your terminal where the script is waiting. |
| 5 | Finish | Your Google Calendar populates with the estimated study blocks. |

