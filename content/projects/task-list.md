---
title: "Task List"
date: 2021-04-15T02:23:29-04:00
slug: "task-list"
description: "This is a simple to-do app that I want to expand into a smart task scheduler."
keywords: ["to-do", "task", "machine learning", "ml", "data science", "UX/UI", "mockflow", "tailwind", "vue.js", "vuetify", "firebase"]
draft: false
tags: ["ML", "UX/UI", "mockflow", "tailwind", "vue.js", "firebase", "JS"]
math: false
toc: true
---

## Current Project

This project (code [here](https://github.com/chase-mortensen/to-do-app)) began as a simple to-do app. The user can add, edit, delete, and mark tasks as complete, as well as filter the list by pending, complete, or all tasks. It isn't fully functional, but you can see a demo [here](https://to-do-app-e6306.firebaseapp.com/). This project was built in Vue.js and is currently styled using vuetify. It is currently hosted using Firebase.

<br>
{{< figure src="/assets/task-list/to-do-current.png" caption="#### Current Version &uarr;" >}}

## What Next?

As I've thought about this fairly standard project, I've realized it doesn't have many interesting advantages over a standard paper to-do list. Sure, it's clean, but it's essentially the same as a physical version. You can add, edit, delete, and mark tasks as complete.

Possible improvements that would give this project a major advantage over a paper to-do list are:
* Incorporate a schedule
* Use ML to estimate task duration
* Suggest tasks for open slots in schedule
* Incorporate other useful fields, such as deadlines and scheduled events
* Categorize tasks
* Use ML to auto-fill fields

## Logical Flow

This is a quick diagram just made in Google Sheets that shows a basic idea of how the project could flow. The image below is a little small, you can see it (along with some additional notes) in more detail [here](https://docs.google.com/presentation/d/1PWH7Dcb5lLijnt8tsesYxikRPbIzDvhJ-ZhCSkN4czA/edit?usp=sharing).

<br>
{{< figure src="/assets/task-list/to-do-flow.png" caption="#### Possible Flow &uarr;" >}}

## Wireframe

I used Mockflow's WireframePro editor to make a few sample desktop pages using Tailwind components (except for the month calandar - Tailwind didn't have that). I'm thinking that the month calandar won't be included in the initial version. If the pages are too small here, you can also see them [here](https://drive.google.com/drive/folders/1_OY3MTGkhcSFj3ZxJU_DuVMTVoZJfu2q?usp=sharing). 

As a disclaimer, there are some pages that have not been created yet - specifically, the settings and sign up pages. There might be other necessary pages as well - this is a rough first draft.

### Login Page

This is state 0 in the diagram. Right now, it's just a standard login page.

<br>
{{< figure src="/assets/task-list/wf-0.png" >}}

### Home Page

This one is state 1. From this page, the user can select a task, add a task, open their profile card, or navigate to settings. The image also shows the default calendar, which has scheduled events in a solid line and suggested events in a dashed line (although it is a little hard to see here). The user can also confirm or delay a suggested task from this state.

<br>
{{< figure src="/assets/task-list/wf-1.png" >}}

Here is the alternative home page showing the month view. Ideally, the user will be able to toggle calendar type in settings.

<br>
{{< figure src="/assets/task-list/wf-1-month.png" >}}

### Task Details

This is state 3 and is shown when a task is selected. From this state, the user can edit or delete a task or deselect the task and return to state 1.

<br>
{{< figure src="/assets/task-list/wf-3-month.png" >}}

### Add/Edit Task

This page is state 4. The edit version is the same as this 'Add Task' page but populates fields with data and changes the title from 'Add' to 'Edit.' From this page, the user can fill out the form and cancel or save the task.

<br>
{{< figure src="/assets/task-list/wf-4-month.png" >}}

### Home Page with Undo

This one is state 5. It is essentially the same as the state 1 home page (although this image is displaying the month calendar), but it shows a toast notification with the option to undo the last action (adding, editing, removing a task, etc.). Pressing undo should undo whatever action was just taken and return the user to the home page.

<br>
{{< figure src="/assets/task-list/wf-5-month.png" >}}

### Profile Card

State 6 is when the profile card is visible and the user is able to edit their personal info or sign out. This page is also displaying the default calandar.

<br>
{{< figure src="/assets/task-list/wf-6.png" >}}

## Conclusion

I am really excited about this project and I think it could be a useful tool for users to better manage their schedules. I think the main next steps would be doing some user testing (maybe a wizard-of-oz test?) and getting feedback. Obviously, the layout and flow makes sense to me since I am the one that designed it. I think the most important thing at this point is getting it in front of some potential users and gaining some new insights to hopefully get out ahead of any UX/UI weak areas.

What do you think? Let me know at chase@chase-mortensen.dev.

Chase
