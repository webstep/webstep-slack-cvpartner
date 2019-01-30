# webstep-slack-cvpartner

Create a slash command function for Slack. Or some kind of event subscription bot? 

Use data from CVPartner to query and retrieve information about consultants' experience, skills and more.

# Simple architecture

1. Use a Slack app with slash command functionality
2. Use an API gateway as our Slack app's endpoint
3. Use serverless Lambda functions to process response from CVPartner

# Search command

To create a command that can search CVPartner we have to learn their search API first.

This is somewhat straightforward using a browser developer toolkit. Let's work on fetching results for consultants with the skill to program in Java.

**Requirements**
1. A [CVPartner account](https://www.cvpartner.com)
2. Install [Postman](https://www.getpostman.com/)

**Steps**
in browser
1. Sign in to CVPartner
2. Select Oversikt from the top nav bar
3. Query for a skill, f.ex "java" with quotation marks
4. Right-click, select inspect to open developer tools
5. Select Network from the menu, filter by 'XHR' and 'Preserve log'
6. Now look for a network request called 'search' in the list of requests. 
7. Select the 'search' request, right click and copy as cURL
in Postman
8. start new request
9. Click on Import in top left of nav bar
10. Select 'Paste raw text' and paste the request we copied from the browser
11. Click import
12. Go back to browser and copy the Request URL
13. Paste Request URL into Postman, and select 'POST' as type
14. Save request for reuse
15. Click send to test request

You should get a Status 200 OK response along with a JSON doc in Postman.

This document contains the first 4 matches for the query for the skill "java". 

### Configuring the request

You can manipulate the number of matches with the `size` parameter in the Request Body. 

### TBD reducing document size

Working with multiple matches, f.ex 10 or more consultants will make the document large. This might be a lot for a serverless function to parse. 

It could be useful to filter the amount of information returned by the Slash command for some basic queries. 

OR the serverless function can be tweaked to return the message in a more suitable format for Slack, to process documents of uneven size and length.
