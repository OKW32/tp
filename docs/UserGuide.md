# Wellness360 User Guide

## Introduction

Wellness360 is a wellness app. It is meant for stressed Engineering Students who prefer CLI over GUI and want to keep track of their overall wellbeing. Our app offers comprehensive tracking and management tools, providing personalized support to alleviate stress and enhance overall well-being. It can help you take control of your mental and physical health effortlessly, so you can focus on your studies with peace of mind.

## Table of Contents
- [Wellness360 User Guide](#wellness360-user-guide)
    - [Starting Wellness360](#quick-start)
    - [Features](#features)
    - [Command Format](#features)
    - [Usage](#usage)
        - Reflection Manager
          - [`reflect get` - Get reflection questions](#get-reflection-questions-reflect-get)
          - [`reflect save` - Save favourite reflection question](#save-favourite-reflection-question-reflect-save)
          - [`reflect unsave` - Unsave favourite reflection question](#unsave-favourite-reflection-question-reflect-unsave)
          - [`reflect list` - View favourite reflection questions](#view-favourite-reflection-questions-reflect-list)
          - [`reflect help` - View reflection help menu](#view-reflection-help-menu-reflect-help)
        - Habit Tracker
          - [`habit add` - Add a new habit](#add-a-new-habit-habit-add)
          - [`habit list` - List out all habits](#list-out-all-habits-habit-list)
          - [`habit update` - Update habit count after completing a habit](#update-habit-count-after-completing-a-habit-habit-update)
          - [`habit delete` - Delete a habit](#delete-a-habit-habit-delete)
          - [`habit set` - Set priority of habit](#set-priority-of-habit-habit-set)
          - [`habit sort` - Sort habit tracker list](#sort-habit-tracker-list-habit-sort)
          - [`habit help` - View habit tracker help menu](#view-habit-tracker-help-menu-habit-help)
        - Sleep Tracker
          - [`sleep add` - Add a new sleep cycle](#add-a-new-sleep-cycle-sleep-add)
          - [`sleep list` - List out all sleep cycles](#list-out-all-sleep-cycles-sleep-list)
          - [`sleep get` - Get hours slept on specific date](#get-hours-slept-on-specific-date-sleep-get)
          - [`sleep update` - Update hours slept on specific date](#update-hours-slept-on-specific-date)
          - [`sleep delete` - Delete sleep cycles](#delete-sleep-cycles-sleep-delete)
            - [Delete Sleep Cycle of a specific date](#delete-sleep-cycle-of-a-specific-date)
            - [Delete Sleep Cycles before a specific date](#delete-sleep-cycles-before-a-specific-date)
            - [Delete Sleep Cycles within a range of dates](#delete-sleep-cycles-within-a-range-of-dates)
          - [`sleep save` - Save sleep cycles](#save-sleep-cycles-sleep-save)
          - [`sleep help` - View sleep tracker help menu](#view-sleep-tracker-help-menu-sleep-help)
        - Focus Timer
          - [`focus switch` - Switch focus timer mode](#switch-focus-timer-mode-focus-switch)
          - [`focus start` - Start a new focus timer](#start-a-new-focus-timer-focus-start)
          - [`focus stop` - Stop the current focus timer](#stop-the-current-focus-timer-focus-stop)
          - [`focus pause` - Pause the current focus timer](#pause-the-current-focus-timer-focus-pause)
          - [`focus resume` - Resume the current focus timer](#resume-the-current-focus-timer-focus-resume)
          - [`focus check` - Check time for focus timer](#check-time-for-focus-timer-focus-check)
          - [`focus set` - Set focus time duration](#set-focus-timer-duration-focus-set)
          - [`focus help` - View focus timer help menu](#view-focus-timer-help-menu-focus-help)
      - Fitness Motivator
          - [`fitness get` - Get a pre-loaded list of different exercises](#get-a-list-of-exercises-fitness-get)
          - [`fitness add` - Add new exercises into the list](#add-exercises-to-the-list-fitness-add)
          - [`fitness delete` - Delete exercises from the list](#delete-exercises-from-the-list-fitness-delete)
          - [`fitness goal` - Set exercise goals for the day](#set-exercise-goals-for-the-day-fitness-goal)
          - [`fitness help` - View Fitness Motivator help menu](#view-fitness-motivator-help-menu-fitness-help)
      - [`exit` - Exit application](#exit-application-exit)
    - [Command Summary](#command-summary)
    - [FAQ](#faq)


## Quick Start

1. Ensure that you have Java 11 or above installed.
2. Download the latest version of `Wellness360` from [here](https://github.com/AY2324S2-CS2113-T11-1/tp/releases).
3. To start `Wellness360` using the `jar` file, go to the containing folder for Wellness360. 
Then, on your terminal of choice, run:
```
-$ java -jar Wellness360.jar
```

## Features

Wellness360 comes with many features for you to manage your well-being using CLI. The 5 main features are Habit 
Tracker, Sleep Tracker, Self Reflection, Focus Timer, and Fitness Motivation.

## Command Format
A command has the general structure:
```
<feature> <command> </arg1> <param1> </arg2> <param2>
```
- Arguments and parameters are not compulsory for all commands. Refer to respective feature commands for specifics.  
- Feature, command and arguments are not case-sensitive to make keying in commands more user-friendly.

## Usage

### Get reflection questions: `reflect get`
Allows user to generate a set of 5 random unique reflection questions from 
a question bank for users to view and reflect on. The questions come 
from 5 main categories: personal growth and development, relationships 
and social connections, career and professional development, health 
and well-being and lastly creativity and personal expression. 
The questions are meant to be randomized for users to think about 
various aspects of their lives. It is not guaranteed to get a 
question from each category. One or more questions may come from the 
same category.  

Format: 
```
reflect get
```
* No additional parameters are allowed, otherwise an error message will be shown.

Example of usage: 
```
reflect get
```
Expected outcome:  
Note that the questions are randomized.
```
________________________________________________________________________________________________________________
1. How do you overcome creative blocks or periods of stagnation?
2. Reflect on a recent professional success. What factors contributed to your achievement?
3. What are your biggest strengths, and how can you leverage them more effectively in your daily life?
4. How do you prioritize self-care and well-being in your daily life?
5. Reflect on a time when you took a creative risk. What did you learn from the experience?
________________________________________________________________________________________________________________
```

### Save favourite reflection question: `reflect save`
Allows user to save reflection question to favourites after viewing generated questions. This allows the user 
to review the question another time. The favourites list is stored in memory as a text file. 
New users will have an empty favourites list file on load, but existing users can load back favourite questions from
past sessions.

Format:
```
reflect save [QUESTION_ID]
```

* Questions that can be saved correspond to the most recent list of generated questions.
* Users need to generate questions before attempting to save it to favourites, otherwise an error message will prompt user to generate questions first.
* `QUESTION_ID` only accepts integers between 1 and 5 inclusive as each list of newly generated questions only contains 5 questions.
* Saving duplicate questions are not allowed, any attempts to do so will result in an error message reminding users that duplicate questions are not allowed.

Example of usage (After generating questions first):
```
reflect save 1
```
Expected outcome:
```
________________________________________________________________________________________________________________
Got it. Added reflection question to favourites:
How do you overcome creative blocks or periods of stagnation?
________________________________________________________________________________________________________________
```

### Unsave favourite reflection question: `reflect unsave`
Allows user to unsave reflection question from favourites list if the question is no longer relevant to the user. The favourites list is stored in memory as a text file.
New users will have an empty favourites list file on load, but existing users can load back favourite questions from
past sessions.

Format:
```
reflect unsave [QUESTION_ID]
```

* Questions that can be unsaved correspond to the reflection questions favourites list.
* If user attempts to unsave a question from an empty favourites list, an error message will prompt user to check range of questions in his favourites list again. 

Example of usage:
```
reflect unsave 1
```
Expected outcome:
```
________________________________________________________________________________________________________________
Got it. Unsaved reflection question from favourites:
How do you overcome creative blocks or periods of stagnation?
________________________________________________________________________________________________________________
```

### View favourite reflection questions: `reflect list`
Allow the user to view favourite reflection questions that have been saved.

Format:

```
reflect list
```
* No additional parameters are allowed, otherwise an error message will be shown.

Example of usage:
```
reflect list
```

Expected outcome:
```
________________________________________________________________________________________________________________
Favourites list:
1. How do you overcome creative blocks or periods of stagnation?
2. How do you prioritize self-care and well-being in your daily life?
3. Reflect on a time when you took a creative risk. What did you learn from the experience?
________________________________________________________________________________________________________________
```

### View reflection help menu: `reflect help`
Allows new users to check what commands are available for reflection feature and their formats.

Format:
```
reflect help
```

* No additional parameters are allowed, otherwise an error message will be shown.

Example of usage:
```
reflect help
```

Expected outcome:
```
________________________________________________________________________________________________________________
Commands for reflection feature:
1. reflect get: Get 5 random reflection questions
2. reflect save <reflection_id>: Save reflection question by id to favourites list
3. reflect unsave <reflection_id>: Unsave reflection question by id from favourites list
4. reflect list: Retrieve questions from favourites list
5. reflect help: Get help menu for reflect commands
________________________________________________________________________________________________________________
```

### Add a new habit: `habit add`
Allow the user to add new habits into the habit tracker.

Format:
```
habit add [HABIT_DESCRIPTION]
```

Example of usage:
```
habit add vacuum and mop the floor
```
Expected outcome:
```
________________________________________________________________________________________________________________
Great! You have added a new habit:
  'vacuum and mop the floor' was successfully added!
________________________________________________________________________________________________________________
```

### List out all habits: `habit list`
Prints a list of all the habits that the user has added into the habit tracker.

Format:
```
habit list
```

* Extraneous parameters will be ignored. For eg, `habit list 123` will be taken as `habit list`


Example of usage:
```
habit list
```

Expected outcome:
```
________________________________________________________________________________________________________________
Here is the list of all your habits!
  1. [LOW] vacuum and mop the floor [count: 2]
  2. [LOW] complete leetcode daily question [count: 3]
________________________________________________________________________________________________________________
```

### Update habit count after completing a habit: `habit update`
Allow the user to update the number of times they have completed a habit. The user will be able to increase the 
count after they have completed the habit during the day. If the user has accidentally increased the count, 
they can decrease the count too.

Format:
```
habit update /id [HABIT_ID] /by [INCREMENT_COUNT]
```

* `HABIT_ID` and `INCREMENT_COUNT` have to be numerical.
* `INCREMENT_COUNT` can be set to 0, but the habit count will remain the same.
* The habit count can only be incremented to a maximum of `2147483647`, which represents the maximum range of an 
integer. Any exceeding count will result in an error message due to integer overflow.

Example of usage (increasing count):
```
habit update /id 2 /by +1
```
* For increasing count, you can omit the positive sign `+` in front, and just type the command as `/by 1`

Expected outcome:
```
________________________________________________________________________________________________________________
Good Job! You have completed your habit!
The count for your habit has been updated:
  2. [LOW] complete leetcode daily question [count: 4]
________________________________________________________________________________________________________________
```

Example of usage (decreasing count):
```
habit update /id 2 /by -2
```
* For decreasing count, you must include a negative sign `-` in front of the count.

Expected outcome:
```
________________________________________________________________________________________________________________
The count for your habit has been updated:
  2. [LOW] complete leetcode daily question [count: 2]
________________________________________________________________________________________________________________
```

### Delete a habit: `habit delete`
Delete a habit from the habit tracker.

Format:
```
habit delete /id <HABIT_ID>
```

* `HABIT_ID` have to be numerical.

Example of usage:
```
habit delete /id 1
```
Expected outcome:
```
________________________________________________________________________________________________________________
Got it! I've removed this habit:
   [LOW] vacuum and mop the floor [count: 2]
Now you have 1 habit left in the list.
________________________________________________________________________________________________________________
```

### Set priority of habit: `habit set`
Set the priority of a habit (`HIGH`, `MED`, `LOW`). Priority of habits are initialised at LOW by default.

Format:
```
habit set /id <HABIT_ID> /priority <PRIORITY_LEVEL>
```

* `HABIT_ID` have to be numerical.
* For `PRIORITY_LEVEL`, user can set as `HIGH`, `MED` OR `LOW` (not case-sensitive).

Example of usage:
```
habit set /id 1 /priority HIGH
```
Expected outcome:
```
________________________________________________________________________________________________________________
The priority for your habit has been updated:
  1. [HIGH] complete leetcode daily question [count: 4]
________________________________________________________________________________________________________________
```

### Sort habit tracker list: `habit sort`
Sort the habits in the habit tracker list according to the habits' priority. 
Habits with higher priority will be placed higher than those with lower priority.

Format:
```
habit sort
```

* Extraneous parameters will be ignored. For eg, `habit sort 123` will be taken as `habit sort`.

Example of usage:
```
habit sort
```
Expected outcome:
```
________________________________________________________________________________________________________________
Habits have been sorted according to priority.
Use `habit list` to view the updated list.
________________________________________________________________________________________________________________
```

### View habit tracker help menu: `habit help`
Allows new users to check what commands are available for habit tracker feature and their formats.

Format:
```
habit help
```

* Extraneous parameters will be ignored. For eg, `habit help 123` will be taken as `habit help`.

Example of usage:
```
habit help
```
Expected outcome:
```
________________________________________________________________________________________________________________
Commands for habit tracker feature:
1. habit add <habit_description>: Add a new habit
2. habit list: List out all existing habits
3. habit update /id <habit_ID> /by <increment_count>: Increase habit count after completing a habit
4. habit delete /id <habit_ID>: Delete a habit
5. habit set /id <habit_ID> /priority <priority_level>: Set priority level for habits (HIGH, MED, LOW)
6. habit sort: Sort habit list according to priority level
________________________________________________________________________________________________________________
```

### Add a new sleep cycle: `sleep add`
Allow the user to add new sleep Cycles into the sleep tracker. Older sleep cycles will be deleted when total hrs reaches
the `MAX_VALUE` for `double`.

Format:
```
sleep add [HOURS_SLEPT] /date [DATE_SLEPT]
```

* `HOURS_SLEPT` will be rounded down to nearest 1 d.p
* `DATE_SLEPT` must be of format dd/MM/yyyy

Example of usage:
```
sleep add 7 /date 18/03/2024
```
Expected outcome:
```
________________________________________________________________________________________________________________
--- SleepCycle for 18/03/2024 has been added ---
________________________________________________________________________________________________________________
```

### List out all sleep cycles: `sleep list`
Prints a list of all the sleep cycles that the user has added into the sleep tracker.

Format:
```
sleep list
```

Example of usage:
```
sleep list
```
Expected outcome:
```
________________________________________________________________________________________________________________
Total hrs slept: 15.0
1. 27/01/2012: 7.0
2. 30/01/2012: 8.0
________________________________________________________________________________________________________________
```

### Get hours slept on specific date: `sleep get`
Prints number of hours slept on specific date.

Format:
```
sleep get [DATE_OF_SLEEP]
```

* `DATE_OF_SLEEP` must be of format dd/MM/yyyy

Example of usage:
```
sleep get 27/01/2012
```
Expected outcome:
```
________________________________________________________________________________________________________________
Hours slept on 27/01/2012: 7.0
________________________________________________________________________________________________________________
```

### Update hours slept on specific date: `sleep update`
Updates number of hours slept on specfic date.

Format:
```
sleep update [DATE_OF_SLEEP] /new [HOURS_OF_SLEEP]
```

* `DATE_OF_SLEEP` must be of format dd/MM/yyyy

Example of usage:
```
sleep update 27/01/2012 /new 9
```
Expected outcome:
```
________________________________________________________________________________________________________________
Hours of sleep for 27/01/2012 has been updated from 7.0 to 9.0
________________________________________________________________________________________________________________
```

### Delete sleep cycles: `sleep delete`

#### Delete Sleep Cycle of a specific date:

Format:
```
sleep delete /date [DATE_OF_SLEEP]
```

* `DATE_OF_SLEEP` must be of format dd/MM/yyyy

Example of usage:
```
sleep delete /date 27/01/2012
```
Expected outcome:
```
________________________________________________________________________________________________________________
Sleep cycle for 27/01/2012 has been removed from list
________________________________________________________________________________________________________________
```
Format:

#### Delete Sleep Cycles before a specific date:

Format:
```
sleep delete /before [DATE_OF_SLEEP]
```

* `DATE_OF_SLEEP` must be of format dd/MM/yyyy

Example of usage:
```
sleep delete /date 27/01/2012
```
Expected outcome:
```
________________________________________________________________________________________________________________
A total of 2 sleep cycles have been deleted
________________________________________________________________________________________________________________
```

#### Delete Sleep Cycles within a range of dates:

Format:
```
sleep delete /from [START_DATE] /to [END_DATE]
```

* `START_DATE` and `END_DATE` must be of format dd/MM/yyyy

Example of usage:
```
sleep delete /from 27/01/2012 /to 27/02/2012
```
Expected outcome:
```
________________________________________________________________________________________________________________
A total of 5 sleep cycles have been deleted
________________________________________________________________________________________________________________
```

### Save sleep cycles: `sleep save`
Allow user to save sleep cycles in a text file located in `FILE_PATH: data/sleep.txt`

Format:
```
sleep save
```

* The `sleep` and `save` are case-sensitive.
* Use lower casing for this command.

Example of usage:
```
sleep save
```
Expected outcome:
```
________________________________________________________________________________________________________________
Saved list to storage file
________________________________________________________________________________________________________________
```

### View sleep tracker help menu: `sleep help`
Allows new users to check what commands are available for sleep tracker feature and their formats.

Format:
```
sleep help
```

Example of usage:
```
sleep help
```
Expected outcome:
```
________________________________________________________________________________________________________________
Commands for sleep tracker feature:
1. sleep add [HOURS_SLEPT] /date [DATE_SLEPT]: Add a new sleep cycle
2. sleep list: List out all sleep cycles
3. sleep get [DATE_OF_SLEEP]: Get hours slept on a specific date
4. sleep update [DATE_OF_SLEEP] /new [HOURS_OF_SLEEP]: Updates hours slept on a specific date
5. sleep delete /date [DATE_OF_SLEEP]: Delete Sleep Cycle of a specific date
6. sleep delete /before [DATE_OF_SLEEP]: Delete Sleep Cycles before a specific date
7. sleep delete /from [START_DATE] /to [END_DATE]: Delete Sleep Cycles within a range of dates
8. sleep save: Allow user to save sleep cycles in a text file located in FILE_PATH: data/sleep.txt
________________________________________________________________________________________________________________
```

### Switch focus timer mode: `focus switch`
Focus timer offers 2 kind of timer for the user. Using `focus switch` command allows user to choose
between count up timer and count down timer.

Format:
~~~
focus switch
~~~

Expected outcome:
~~~
________________________________________________________________________________________________________________
Switched to Count down timer
________________________________________________________________________________________________________________
~~~
* Outcome depends on the current timer mode.
* `focus switch` will be disable if a timer is currently running.
* Extraneous parameters for this command will be ignored. For example: `focus switch 123` will be taken as `focus switch`.

### Start a new focus timer: `focus start`
Allow the user to start a new focus timer session. The user will be able
to start the timer whenever they want and the application will keep track of the time.
In addition, only 1 timer will run at a time, thus multiple uses of `focus start` is not allowed.

Format:
~~~
focus start
~~~
* Extraneous parameters for this command will be ignored. For example: `focus start 123` will be taken as `focus start`.

Expected outcome:
* Count up timer.
~~~
________________________________________________________________________________________________________________
Your session has started. Time to grind!
________________________________________________________________________________________________________________
~~~

* Count down timer.
~~~
________________________________________________________________________________________________________________
Countdown timer started! 
Duration set: 1 minute(s) 0 second(s)
________________________________________________________________________________________________________________
~~~

### Stop the current focus timer: `focus stop`
> <strong><img class="emoji" title=":information_source:" alt=":information_source:" src="https://github.githubassets.com/images/icons/emoji/unicode/2139.png" height="20" width="20"> NOTE: <Br>
> * Countdown timer will automatically stop when the duration expires.
>
Allow users to stop a timer that is currently running. The users will be able to see the total
time elapsed upon a successful stop.

Format:
~~~
focus stop
~~~

* Extraneous parameters for this command will be ignored. For example: `focus stop 123` will be taken as `focus stop`.

Expected outcome:
* Count up timer
~~~
________________________________________________________________________________________________________________
Your focus session has ended.
 Time spent: X hours, X minutes, XX seconds
To start a new session, use ‘focustimer start’ 
________________________________________________________________________________________________________________
~~~

* Count down timer
* Timer will automatically stop if the duration expires. However, users will still be able to stop it manually
~~~
________________________________________________________________________________________________________________
3 seconds left
________________________________________________________________________________________________________________
________________________________________________________________________________________________________________
2 seconds left
________________________________________________________________________________________________________________
________________________________________________________________________________________________________________
1 seconds left
________________________________________________________________________________________________________________
________________________________________________________________________________________________________________
Count down timer completed!
________________________________________________________________________________________________________________
~~~

> <strong><img class="emoji" title=":warning:" alt=":warning:" src="https://github.githubassets.com/images/icons/emoji/unicode/26a0.png" height="20" width="20">
 Warning:
> * The countdown timer will display the above messages when there are 3 seconds left on the timer, which may disrupt user input. Please wait until the timer is up before trying to input new commands into the CLI, as this is part of the countdown timer feature.

### Pause the current focus timer: `focus pause`
Allow users to pause the timer momentarily while the timer is running.

Format:
~~~
focus pause
~~~

* Extraneous parameters for this command will be ignored. For example: `focus pause 123` will be taken as `focus pause`.

Expected outcome:
* Count up timer
~~~
________________________________________________________________________________________________________________
Count up timer paused.
________________________________________________________________________________________________________________
~~~

* Count down timer
~~~
________________________________________________________________________________________________________________
Timer paused. 
Remaining time: 0 minutes 56 seconds
________________________________________________________________________________________________________________
~~~
### Resume the current focus timer: `focus resume`
Allow users to resume the paused timer.

* Extraneous parameters for this command will be ignored. For example: `focus resume 123` will be taken as `focus resume`.

Format:
~~~
focus resume
~~~

Expected outcome:
* Count up timer
~~~
________________________________________________________________________________________________________________
Count up timer resumed
________________________________________________________________________________________________________________
~~~

* Count down timer
~~~
________________________________________________________________________________________________________________
Countdown timer resumed.
________________________________________________________________________________________________________________
~~~

### Check time for focus timer: `focus check`
Allow users to check the total time elapsed or total time remaining, depending on the mode of the timer.

Format:
~~~
focus check
~~~

* Extraneous parameters for this command will be ignored. For example: `focus check 123` will be taken as `focus check`.

Expected outcome:
* Count up timer
~~~
________________________________________________________________________________________________________________
Total time elapsed: 
0 hours, 0 minutes, 8 seconds
________________________________________________________________________________________________________________
~~~

* Count down timer
~~~
________________________________________________________________________________________________________________
Remaining time: 
0 minutes 54 seconds left.
________________________________________________________________________________________________________________
~~~

### Set focus timer duration: `focus set`
> <strong><img class="emoji" title=":bulb:" alt=":bulb:" src="https://github.githubassets.com/images/icons/emoji/unicode/1f4a1.png" height="20" width="20"> Tip: 
> * Using `focus set`  command only affects count down timer. 
>

Allow users to set the desired countdown timer duration in minutes for the session.

Format:
~~~
focus set [minutes]
~~~
* Input `minutes` must be in numerical form and can be more than 60.
* Example: *120 minutes implies 2 hours*
* Input `minutes` cannot be more than `MAX_VALUE: 2,147,483,647`.
* Extraneous parameters for this command will be ignored. For example: `focus set 10 123` will be taken as `focus set 10`.

Example of usage:
~~~
focus set 10
~~~

Expected outcome:
~~~
________________________________________________________________________________________________________________
Countdown duration has been set to 10 minute(s)
________________________________________________________________________________________________________________

~~~

### View focus timer help menu: `focus help`
Allows new users to check what commands are available for focus timer feature and their formats.

Format:
~~~
focus help
~~~

* Extraneous parameters will be ignored. For eg, `focus help 123` will be taken as `focus help`.

Example of usage:
~~~
focus help
~~~

Expected outcome:
~~~
________________________________________________________________________________________________________________
Commands for focus timer feature:
1. focus switch: Switch between count up timer and count down timer
2. focus start: Start the timer
3. focus stop: Stop the timer
4. focus pause: Pause the timer
5. focus resume: Resume the timer
6. focus set [minutes]: Set the desired countdown timer duration in minutes
________________________________________________________________________________________________________________
~~~

### Get a list of exercises: `fitness get`
Prints a list of exercises. If no parameters are specified, 5 different exercises from 5 different types of exercises 
targeting different body parts. If the exercise type is specified, only exercises matching that type will be shown.

Format:
```
fitness get [EXERCISE_TYPE]
```

* Running the command with no parameters will generate different exercises with each repeated command, but there should be one exercise from
  each type
* The `[EXERCISE_TYPE]` parameter is optional, and only supports the following types:
  * Arms, Chest, Abs, Back, Legs (Not Case Sensitive)

Example of usage (getting exercises of a certain type):
~~~
fitness get
~~~

Expected outcome:
```
________________________________________________________________________________________________________________
These are some of the exercises you can do! LETS GET STRONK MY G

1. Arms: Skullcrushers, 3 sets & 8 reps
2. Chest: Cable Flies, 3 sets & 8 reps
3. Abs: Crunches, 5 sets & 20 reps
4. Back: Lateral Rows, 3 sets & 8 reps
5. Legs: Leg Press, 3 sets & 8 reps

________________________________________________________________________________________________________________
```
Example of usage:
~~~
fitness get arms
~~~

Expected outcome:
```
________________________________________________________________________________________________________________
Here are the Arms exercises as requested!

1. Arms: Cable Triceps Push down, 3 sets & 8 reps
2. Arms: Barbell Curls, 3 sets & 8 reps
3. Arms: Preacher Curls, 3 sets & 8 reps
4. Arms: Skullcrushers, 3 sets & 8 reps
5. Arms: Lateral Raises, 3 sets & 8 reps
________________________________________________________________________________________________________________

```


### Add exercises to the list: `fitness add`
Allows the user to add their own exercises to the list of exercises.

Format:
```
fitness add /type [EXERCISE_TYPE] /name [EXERCISE_NAME] /sets [NUMBER_OF_SETS] /reps [NUMBER_OF_REPS]
```

* The `[EXERCISE_TYPE]` parameter only supports the following types:
  * Arms, Chest, Abs, Back, Legs (Not Case Sensitive)

Example of usage:
```
fitness add /type Arms /name Tricep Dips /sets 8 /reps 10
```

Expected outcome:
```
________________________________________________________________________________________________________________
I have added the following exercise into our list!
Arms: Tricep Dips, 8 sets & 10 reps
________________________________________________________________________________________________________________
```

### Delete exercises from the list: `fitness delete`
Allows the user to delete exercises from the list of exercises.

Format:
```
fitness delete [EXERCISE_TYPE] [INDEX]
```

* The `[EXERCISE_TYPE]` parameter only supports the following types:
    * Arms, Chest, Abs, Back, Legs (Not Case Sensitive)
* Use the `fitness get [EXERCISE_TYPE]` command to find out the indexes of the respective exercises
* The printed list of exercises reflects the list of exercises left that are of the same type as the exercise deleted.

Example of usage:
```
fitness delete arms 6
```
Expected Outcome:
```
________________________________________________________________________________________________________________
 I have deleted the exercise. Here are the exercises left in the list!

1. Arms: Cable Triceps Push down, 3 sets & 8 reps
2. Arms: Barbell Curls, 3 sets & 8 reps
3. Arms: Preacher Curls, 3 sets & 8 reps
4. Arms: Skullcrushers, 3 sets & 8 reps
5. Arms: Lateral Raises, 3 sets & 8 reps
________________________________________________________________________________________________________________

```

### Set exercise goals for the day: `fitness goal`
Allows the user to create, track and mark a list of exercise goals.

Formats:
```
fitness goal
fitness goal new
fitness goal [INDEX]
```

* Running the command with no parameters will generate different exercises goals with each repeated command.
* Use the `fitness goal` command to find out the indexes of the respective exercises goals.
* Use the `fitness goal new` command to get a new randomised list of five exercise goals.
* Running `fitness goal new` will always override any previously set goals.
* Use the `fitness goal [INDEX]` command to mark/unmark a specific goal. 
* Only `new` and `[INDEX]` are accepted as parameters, where `[INDEX]` is an integer value. The parameters are optional as well.

Example of usage :
```
fitness goal
```

Expected outcome (If there are no current goals):
```
________________________________________________________________________________________________________________
There are no goals set :(

You can set one by doing 'goal new'!
________________________________________________________________________________________________________________
```

Expected outcome (If there are goals already set):
```
________________________________________________________________________________________________________________
Lets get working on today's exercises!

1. [ ] Arms: Skullcrushers, 3 sets & 8 reps
2. [ ] Chest: Wide Arm Push-up, 3 sets & 15 reps
3. [ ] Abs: Weighted Sit-Ups, 3 sets & 20 reps
4. [ ] Back: Weighted Pull Ups, 3 sets & 6 reps
5. [ ] Legs: Calf Raises, 3 sets & 10 reps

________________________________________________________________________________________________________________
```

Example of usage :
```
fitness goal new
```

Expected outcome:
```
________________________________________________________________________________________________________________
Lets get working on today's exercises!

1. [ ] Arms: Skullcrushers, 3 sets & 8 reps
2. [ ] Chest: Wide Arm Push-up, 3 sets & 15 reps
3. [ ] Abs: Weighted Sit-Ups, 3 sets & 20 reps
4. [ ] Back: Weighted Pull Ups, 3 sets & 6 reps
5. [ ] Legs: Calf Raises, 3 sets & 10 reps

________________________________________________________________________________________________________________
```

Example of usage:
```
fitness goal 3
```

Expected outcome:
```
________________________________________________________________________________________________________________
I see there are changes. I hope you are making progress...

1. [ ] Arms: Skullcrushers, 3 sets & 8 reps
2. [ ] Chest: Wide Arm Push-up, 3 sets & 15 reps
3. [X] Abs: Weighted Sit-Ups, 3 sets & 20 reps
4. [ ] Back: Weighted Pull Ups, 3 sets & 6 reps
5. [ ] Legs: Calf Raises, 3 sets & 10 reps

________________________________________________________________________________________________________________
```

### View Fitness Motivator help menu: `fitness help`
Allows the user to see a list of available commands that can be executed under the FitnessMotivator.

Format:
```
fitness help
```

Example of usage:
```
fitness help
```
Expected Outcome:
```
________________________________________________________________________________________________________________
Here is a list of possible commands you can use with the Fitness Motivator!

1. fitness get: Get 5 random exercises each of different type.
2. fitness get <exercise_type>: Get a full list of exercises belonging to the exercise type
3. fitness add /type <exercise_type> /name <exercise_name> /sets <sets> /reps <reps>: 
add an exercise to the list of exercises
4. fitness delete <exercise_type> <index>: Delete the exercise from the list of exercise.
The index is based on the index when you run 'fitness get <exercise_type>
5. fitness goal: Retrieves the status of all current goals, if it exists
6. fitness goal new: Overwrites current goals with new set of goals if it exists, 
otherwise creates a brand new set of goals
7. fitness goal <index>: Toggle the status of the goal
8. fitness help: Get help menu for reflect commands
________________________________________________________________________________________________________________
```

### Exit application: `exit`
Allows user to exit Wellness360 application.

Format:

```
exit
```

* No additional parameters are allowed, otherwise an error message will be shown.

Example of usage:

```
exit
```

Expected outcome:
```
________________________________________________________________________________________________________________
Goodbye! See you again!
________________________________________________________________________________________________________________
```

## Command Summary

This section serves as a cheatsheet for commands.

| **Command**                                                                                             | **Description**                              |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------|
| `reflect get`                                                                                           | Get 5 random reflection questions            |
| `reflect save [QUESTION_ID]`                                                                            | Save favourite reflection question           |
| `reflect unsave [QUESTION_ID]`                                                                          | Unsave favourite reflection question         |
| `reflect list`                                                                                          | View favourite reflection questions          |
| `reflect help`                                                                                          | View reflection help menu                    |
| `habit add [HABIT_DESCRIPTION]`                                                                         | Add a new habit                              |
| `habit list`                                                                                            | List out all habits                          |
| `habit update /id [HABIT_ID] /by [INCREMENT_COUNT]`                                                     | Update habit count after completing a habit  |
| `habit delete /id [HABIT_ID]`                                                                           | Delete a habit                               |
| `habit set /id [HABIT_ID] /priority [PRIORITY_LEVEL]`                                                   | Set priority of habit                        |
| `habit sort`                                                                                            | Sort habit tracker list                      |
| `habit help`                                                                                            | View habit tracker help menu                 |
| `sleep add [HOURS_SLEPT] /date [DATE_SLEPT]`                                                            | Add a new sleep cycle                        |
| `sleep list `                                                                                           | List out all sleep cycles                    |
| `sleep get [DATE_OF_SLEEP]`                                                                             | Get hours slept on specific date             |
| `sleep update [DATE_OF_SLEEP] /new [HOURS_OF_SLEEP]`                                                    | Update hours slept on specific date          |
| `sleep delete /date [DATE_OF_SLEEP]`                                                                    | Delete Sleep Cycle of a specific date        |
| `sleep delete /before [DATE_OF_SLEEP]`                                                                  | Delete Sleep Cycles before a specific date   | 
| `sleep delete /from [START_DATE] /to [END_DATE]`                                                        | Delete Sleep Cycles within a range of dates  | 
| `sleep save`                                                                                            | Save sleep cycles                            |
| `sleep help`                                                                                            | View sleep tracker help menu                 |
| `focus switch`                                                                                          | Switch focus timer mode                      |
| `focus start`                                                                                           | Start a new focus timer                      |
| `focus stop`                                                                                            | Stop the current focus timer                 |
| `focus pause`                                                                                           | Pause the current focus timer                |
| `focus resume`                                                                                          | Resume the current focus timer               |
| `focus check`                                                                                           | Check time for focus timer                   |
| `focus set [minutes]`                                                                                   | Set focus time duration                      |
| `focus help`                                                                                            | View focus timer help menu                   |
| `fitness get`, `fitness get [EXERCISE_TYPE]`                                                            | Get a pre-loaded list of different exercises |
| `fitness add /type [EXERCISE_TYPE] /name [EXERCISE_NAME] /sets [NUMBER_OF_SETS] /reps [NUMBER_OF_REPS]` | Add new exercises into the list              |
| `fitness delete [EXERCISE_TYPE] [INDEX]`                                                                | Delete exercises from the list               |
| `fitness goal`, `fitness goal new`, `fitness goal [INDEX]`                                              | Set exercise goals for the day               |
| `fitness help`                                                                                          | View Fitness Motivator help menu             |
| `exit`                                                                                                  | Exit application                             |


## FAQ

**Q**: How do I transfer my data to another computer?

**A**: After first time usage, if any data was saved during the session, it will be stored as text files under docs folder. Copy it over to
another computer if you wish.

**Q**: Can I directly edit the text files that are meant as data storage?

**A**: Absolutely not. Do not edit the text files directly. Only interact with the storage text files via commands when running the jar file.

**Q**: What will happen if I accidentally edited the text files?

**A**: Behaviour of application might become unpredictable as the text files may become corrupted. We recommend manually deleting corrupted text files and restarting the jar file.
New text files will be created to replace the missing files, and you can continue using the app as usual. Note that by deleting the text files, any past data stored on it would be wiped.
To prevent loss of data and having to remove corrupted files, DO NOT attempt to edit the text files directly as mentioned previously.