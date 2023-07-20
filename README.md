# Inscription Pipeline

General Idea of things that need to be done:
- Get specs for server (RAM, hard drive, any CPU requirements to run the models?)
- Have a bash script that runs once every hour on a cron
- Bash script will run a series of Python scripts
- Script #1: Find new inscriptions from API, download them locally, add them to inscription “database” csv file, mark as in progress
- Script #2: Pull all in progress inscriptions, assign appropriate mime type
- Script #3: Pull all in progress inscriptions, filter for images, run image captioning, append tags
- Script #4: Pull all in progress inscriptions, filter for images, run color tagging, append tags
- Script #5: Pull all in progress inscriptions, filter for JSON, add protocol tagging
- Script #6: Submit all tags, keywords, content type to firestore db, mark as finished (not in progress anymore)