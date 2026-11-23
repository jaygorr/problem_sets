# Descriptions of columns in data file

(each row is data from one trial)

* `blockNum`: the block number of that given trial. All learning trials are 0, transfer trial is 1
* `stimType`: the type of the stimulus pair presented on the given trial (e.g., shapes means the two options on the trial were geometric shapes)
* `simpleStim`: the index of the simple stimulus (from the simple stimulus options). In this case, it can also be the set of numbers used in the mathematical expression.
* `complexStim`: the index of the complex stimulus (from the complex stimulus options). When `stimType` is `math`, this will be those same numbers with additional formatting for the expressions.
* `isTransferTrial`: whether the trial is a transfer trial. 0 if learning, 1 if transfer
* `complexPosition`: whether the complex stimulus is in the left or right box on the trial
* `rewardCondition`: whether the subject is rewarded for choosing the complex option on each trial or the simple option on each trial
* `trialID`: trial number
* `response`: participant response (whether they chose the right or left box)
* `rt`: response time (msec) from the presentation of the options to when the participant responded
* `gotReward`: whether the subject chose the correct (i.e., reward-earning) answer on that trial
* `subjectID`: anonymized participant identity
* `experimentName`: experiment name
* `experimentVersion`: experiment version
* `experimentTime`: duration of the experiment (in msec)
* `studyID`: study ID from Prolific (always 0 here)
* `sessionID`: session ID from Prolific (always equal to anonymized subjectID here)
* `browserName`: web browser name
* `browserVersion`: web browser version
* `displayWindowHeight`: browser window height (in pixels)
* `displayWindowWidth`: browser window width (in pixels)
* `displayScreenHeight`: screen height (in pixels)
* `displayScreenWidth`: screen width (in pixels)
* `purposeGuess`: participant's post-experiment guess about the purpose of the study
* `taskGuess`: participant's post-experiment description of the task they had to complete
* `strategyLearn`: participant's post-experiment description of how they made their choice in the learning phase of the task
* `strategyTransfer`: participant's post-experiment description of how they made their choice on the transfer trial
* `commentText`: participant's post-experiment comments on the study
* `totalTime`: duration of the entire study from instructions to submission (in msec)
