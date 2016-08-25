# siggydeltawarnings
A simple tool that monitors your Siggy chain and the NPC kills from the XML API and alerts you when a system near your home has a high delta. The goal of this is to give members of your corporation nudges to go hunting in an automated and useful way.

![Screenshot of the Slack message](screenshot.png?raw=true)

## Running it
You have a few ways to run this script. The easiest, if you have Docker, is to simply run the following:

    docker run -d -e SLACK_WEBHOOK=https://hooks.slack.com/web/hook/url/here -e HOME_SYSTEM_ID=12345678 -e SIGGY_USERNAME=username -e SIGGY_PASSWORD=something_secure regner/siggydeltawarnings

### Environment Variables
* **HOME_SYSTEM_ID:** Required. The ID of your home system.
* **SLACK_WEBHOOK:** Required. The webhook URL generated by Slack and pointing to the channel you want the messages to go to.
* **SIGGY_USERNAME:** Required. Username to log into Siggy with.
* **SIGGY_PASSWORD:** Required. Password to log into Siggy with.
* **MIN_DELTA:** Defaults to 150. The minimum required delta for a system to be considered.
* **MAX_JUMPS:** Defaults to 20. The maximum number of jumpts from your home system