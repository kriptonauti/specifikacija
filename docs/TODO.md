# Overview

The repo is using the OMDNBNI 3ID project management model.

----
> The tasks are organized into a Markdown table, stored in a [TODO.md](../TODO.md) file

----
> The task current state, history and activity can be tracked through the file version history

----
> Only the `master` branch is considered valid.

----

## Task states

The tasks can be in the following states.

| State | Description |
|:-----:|:----------- |
| *pending*    | The **task** is pending to start.
| EVOLVING     | The **task** is being worked on.
| stalled      | The **task** has been started but has been stalled.
| ~~canceled~~ | The **task** has been started but was canceled and will not be worked on until further notice.
| **resolved** | The **task** has been completed.

## Task priorities

The task priorities are standard integer based priority ranks where the priority is the inverse of the rank.

> The lower the priority is, the higher the priority is.

----
> Only **resolved** OR ~~canceled~~ **tasks** can have a priority of ***zero***

----

## Task assignees

The assignees can be found in the [README.md](../README.md#osnivači)

| 3ID prefix | Description |
|:----------:|:----------- |
| **?** | The **assignee** is nominated to manage the task, pending consensus disapproval and nominee acceptance.
| **_** | The **assignee** has accepted the responsibility for the managing the task by the consensus.
| **!** | The **assignee** has forcibly taken the responsibility for managing the task w/o consensus approval.


## Task deadlines

The task deadline is an *optional* field stating the deadline for resolving the task in [ISO-8601 format](https://en.wikipedia.org/wiki/ISO_8601).

| Format | Description |
|:------:|:----------- |
| YYYY-MM-DD | Expecting to meet the deadline.
| *YYYY-MM-DD* | Expecting to miss the deadline by less than 24h.
| **YYYY-MM-DD** | Expecting to miss the deadline by more than 24h.
| ~~YYYY-MM-DD~~ | Deadline missed.

## Example

| State | Priority | Assignee | Deadline | Description |
|:-----:|:--------:|:--------:|:--------:|:----------- |
| *pending* | **20** | ?ana |            | @ana is being nominated for *this* task.
| *pending* | **20** | _bil |            | @bil has accepted to manage *this* task w/o a deadline.
| *pending* | **20** | !dag | 2018-03-11 | @dag has taken controll over *this* task with a deadline.
| *pending* | **10** | _che | 2018-03-10 | @che has accepted to manage *this* task.
| EVOLVING | **10** | _bil | 2018-03-01 | @bil is working on this task and is on time.
| EVOLVING | **10** | _bil | 2018-03-01 | @bil is working on this task and is on time.
| EVOLVING | **10** | _che | *2018-03-02* | @che is working on this task and is expecting to miss the deadline by a little bit.
| stalled | **20** | _eve | 2018-03-01 | @eve has stalled on this task but is expecting to meet the deadline.
| EVOLVING | **20** | _ana | **2018-03-01** | @ana is working on this task but is expecting to totaly miss the deadline.
| EVOLVING | **20** | _eve |            | @eve is working on this task w/o a deadline.
| stalled | **30** | _dag | 2018-03-03 | @dag has stalled on this task.
| **resolved** | **10** | _bil | 2018-01-10 | @bil has resolved the task
| ~~canceled~~ | **20** | _ana | ~~2018-01-11~~ | @ana has been working on this task, the deadline was missed, and it was canceled.
| **resolved** | **25** | !dag | ~~2018-02-01~~ | @dag has resolved this task, the deadline has been missed, and it was done unilaterally.
| ~~canceled~~ | **30** | _ana |            | @ana has been working on this task w/o a deadline and it was cancelled.
| **resolved** | **40** | _che | 2018-02-15 | @che has resolved this task, meeting the deadline.
| **resolved** | **10** | !eve | *2018-02-16* | @eve has unilaterally resolved this task, only slightly missing the deadline
| **resolved** | **30** | _bil | 2018-02-17 | @bill has completed this task with a deadline.
