# Authorization

Regular Bing Ads authorization is handled as follows:

- User logs into Bing Ads, using their user name or email address and password.
- Bing Ads authenticates the user's credentials and establishes a session.
- During the active session, the user is authorized to manage campaigns.

Scripts are different because they may run while there is no active user session:
- Scheduled scripts will execute periodically, independent of whether the user is logged in at the time.
- Scripts may execute for a duration of up to 30 minutes. The user may log out of Bing Ads before the script run completes.

Scripts are essentially independent entities that take campaign management actions on behalf of the user.