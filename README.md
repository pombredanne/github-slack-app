# github-slack-app
A minimalist github-to-slack integration where you are in control working around thread spam https://github.com/integrations/slack/issues/1500

Design outline:

- a (Python?) command line app that takes as inputs a Slack API key, a GitHub API key, a Slack org/channel to push notifications to and a GitHub org/repo to pull notifications from
- the app would
  - create an incomming webhook on the Slack side
  - create an outgoing webhook on the GitHub side

The needs for this is to be in control of notifications flow and avoid the threads spam from the GitHub "official" integration.
The flow is overall this: https://github.com/integrations/slack/issues/1500#issuecomment-1292175225

> A workaround :
> 1. on the slack side, go to "manage apps"
> 2. select custom integration. Ignore this mumbo jumbo: "We recommend replacing your custom integrations with Slack apps, which have more features and use the latest APIs. Learn more about switching to Slack apps.". duh.
> 3. select "Incoming WebHooks", then "add to slack"
> 4. In "choose a channel" enter the channel you want to have notifications posted, then "Add Incoming WebHooks integration"
> 5. Copy the webook URL ... e.g., "https://hooks.slack.com/services/T03Hxxxxxxxxxxxxxxxxxxx"
> 6. On the Github side, go to a project "Settings"
> 7. Select "Webhooks" then "Add webhook"
> 8. In the "Payload URL" field paste the webhook URL from 5. 
> 9.  Select "Content Type"  as application/json
> 10. Select which GH events you want to broadcast (defaults is just push)
> 11. Click "Add webhook" 
> 
> Done!
