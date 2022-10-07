#Go Review Me

Simple slackbot that will choose from a list of default reviewers to review a PR 

Thoughts about how this should work... 
- Should be able to communicate with git server (in our case bitbucket, but could add other integrations later)
- Bitbucket hook that makes a request to the az func endpoint when there is a new PR
- Go client should be able to fetch the default reviewers for the project and round robin select the next user to 
review
    - Guess it should hold some state about last reviewer picked
    - It would be nice to do some weighted round robin so people that have recently reviewed are not picked as quickly next time
    - Or could just randomly select a user and remove the last person to review from random pool
- Message user in slack with link to PR
    - maybe have a channel set up for the default reviewers of the project? 
    - or message them directly
- Give option to accept or decline reviewing PR
    - if the accept save them in state that they were last reviewer
    - if the decline, pick another user 

