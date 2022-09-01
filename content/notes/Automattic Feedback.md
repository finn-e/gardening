---
title: "Automattic Feedback"
status: Early
sureness: Low
---
# Automattic Feedback

First and foremost, we really appreciate your hard work on the test. Our engineering team has now had a chance to review your completed test, and unfortunately we cannot move forward with the process at this time. The high volume of qualified applications we receive often forces us to make difficult decisions. Although I’m sure this isn’t the news you were hoping to hear, you should be proud of how far you made it in the interview process!In the spirit of sharing feedback here are one or two things that we think went well for you on the test:  

-   The solution works in most scenarios, and provides feedback to the user about the changes made.
-   The solution included helpful information about the current implementation and its performance, and commit messages provided context about the changes made.
-   The solution takes performance into consideration, taking advantage of bulk delete and insert operations.

Several things could have gone better including:  

-   Performance could be improved. Looping through each local name and checking the list of remote names with `array_search` and `in_array` slowed the command down quite a bit when the local list had more than a few names in it (e.g: the second time it runs). It would also have been great to see updates and deletions to the names data being executed in bulk queries instead of one at a time.
-   Error handling could be improved. Getting the remote list and interfacing with the DB are two areas where errors can easily arise and should be handled.
-   When a local name is found in the first position of the `$add_list`, we will always mark it as outdated or delete it. This is because the result of`if (! $in_remote)` [here](https://github.com/automattic-hiring/backend-v2-code-test-finn-e/pull/1/files#diff-2ab0e58c89d15aaf1a9865cc688df49b35204c1b2c7884fd9aa4371f4da05e51R82-R83) will be true when the result of `array_search` is the valid index `0`.
-   The solution did not include any automated tests, or detailed test instructions for manual testing that would help validate all critical path scenarios.

Again, we appreciate your  time and patience in undertaking the test. If it aligns with your goals, we encourage you to apply for any VIP or Automattic position after 12+ months. We wish you all the best! ![:meow-flower:](https://emoji.slack-edge.com/T024FN1V2/meow-flower/853f466fe811e14f.png)