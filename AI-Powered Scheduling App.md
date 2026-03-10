BYUI Canvas API Token
  
10706~CafnnYz6YPcryUPMyUEXDN4fDvUJhkyMLWCJuPUfxntXrcEwR6hNY9J74HFyUXFM

Networking Canvas API Token

7~t69XWHfzrZR9uZvQEnvtRmBBJQKPt3yFmwEE6UFTYnxQCEJcn9v6ZPFwU23UkvAx

Custom Tasks:

{
        "course": "Ancient Greek II",
        "name": "Between-Class Translation & Prep",
        "due_at": "Prior to 12:45 PM on Monday", 
        "description": "Requires about 2 hours of focused study and translation work to be done prior to the class following the one it was assigned in. Can be broken into smaller blocks."
    },
    {
        "course": "Ancient Greek II",
        "name": "Between-Class Translation & Prep",
        "due_at": "Prior to 12:45 PM on Tuesday", 
        "description": "Requires about 2 hours of focused study and translation work to be done prior to the class following the one it was assigned in. Can be broken into smaller blocks."
    },
    {
        "course": "Ancient Greek II",
        "name": "Between-Class Translation & Prep",
        "due_at": "Prior to 12:45 PM on Wednesday", 
        "description": "Requires about 2 hours of focused study and translation work to be done prior to the class following the one it was assigned in. Can be broken into smaller blocks."
    },
    {
        "course": "Ancient Greek II",
        "name": "Between-Class Translation & Prep",
        "due_at": "Prior to 12:45 PM on Thursday", 
        "description": "Requires about 2 hours of focused study and translation work to be done prior to the class following the one it was assigned in. Can be broken into smaller blocks."
    }


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

Here is the updated master prompt. I have integrated the Free/Busy retrieval into Phase 1 and updated the meta-prompt instructions so Gemini knows exactly which time blocks are strictly off-limits.
🚀 The Refined Master Prompt
Copy and paste the text below into Gemini 3.1 Pro:
> I need you to write a Python script that automates a 3-step academic scheduling workflow. Since I do not have access to the Gemini API keys, the script must function in two distinct phases with a manual copy-paste step in the middle.
> Phase 1: Data Extraction & Prompt Generation
>  * Canvas Integration: Use the Canvas LMS REST API (using a Bearer Token) to fetch my current 'To-Do' list from /api/v1/users/self/todo.
>  * Detail Retrieval: For each assignment found, use the course_id and assignment_id to fetch the full assignment object from /api/v1/courses/{course_id}/assignments/{assignment_id}.
>  * Data Cleaning: Use BeautifulSoup to strip all HTML tags from the assignment description field so it is clean text.
>  * Free/Busy Retrieval: Use the Google Calendar API (Freebusy: query endpoint) to fetch my existing busy times on my 'primary' calendar. The time range should be from the current datetime until the furthest assignment due date (or a default of 14 days from now if no due dates are found).
>  * The 'Meta-Prompt': The script should then print a large, well-formatted text block to the console. This block is a prompt meant for ME to copy and paste into Gemini. It should contain:
>    * Clear instructions for Gemini to perform a 'Deep Thinking' task analysis.
>    * The current date, time, and timezone (dynamically generated by the script) so Gemini knows exactly when "now" is.
>    * A compiled list of my Existing Busy Times (in ISO 8601 format), with explicit instructions for Gemini not to schedule any new blocks that overlap with these times.
>    * The clean text and due dates of all my assignments.
>    * A request for Gemini to return a specific, minified JSON object containing: task_name, estimated_total_hours, and calendar_blocks (an array of suggested start/end times).
>    * Crucial: Instruct Gemini that all start/end times in the JSON MUST be in strict ISO 8601 format.
> Phase 2: Manual Input & Calendar Integration
>  * User Input: Python's standard input() can struggle with pasting large multi-line JSON payloads. Instead, have the script use sys.stdin.read() to capture multi-line input until an EOF character is passed, OR prompt the user to save the AI's JSON output to a local schedule.json file and hit Enter to continue.
>  * Google Calendar Integration: Use the Google Calendar API (OAuth2) to parse that JSON and create the actual time blocks on my 'primary' calendar.
> Technical Constraints:
>  * Use requests for Canvas and google-api-python-client / google-auth-oauthlib for Google.
>  * Include error handling for expired Canvas tokens.
>  * Ensure the Google Calendar part handles timezones accurately using datetime and pytz.
>  * Provide a clear 'Setup' section in the comments explaining where to put the credentials.json for Google and the CANVAS_TOKEN.
> 
💡 Why this makes a massive difference:
By using the Freebusy: query endpoint rather than pulling full event details, your script will respect your privacy (it won't pass personal event titles to the AI) while ensuring that Gemini acts as a flawless scheduling assistant that perfectly weaves your study blocks into your actual availability.

