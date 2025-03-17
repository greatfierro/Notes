

**Authorization**
- Prevent users from reading others Jits



Features

User will be able to see all the users they are following Jits

Clicking on a users profile will show you all their jits
	- If the user has a private profile, then no jits will show




**Profile Endpoint**
	- View profile info
	- Get newsfeed


[**Relationship Endpoint**](obsidian://open?vault=Notes&file=JitAPI%2FRelationship%20Table)
Endpoint to manage relationships between users
*Requirements*
1. User must be logged in
*Actions*
* Follow
	* Default action when approval is not required.
- Remove
	- Allow logged in user to stop following another user.
- Request
	- If **Follow** is not successful, then request a follow.