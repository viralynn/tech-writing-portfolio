---
title: DoubtQueue README Features section
sidebar_label: DoubtQueue README features
description: "A Features section for the DoubtQueue README, written for issue #30, with every line checked against the running app."
---

:::note[Attribution]
This page describes my documentation work on [DoubtQueue](https://github.com/NxtLabTech/DoubtQueue), written for [issue #30](https://github.com/NxtLabTech/DoubtQueue/issues/30). I checked every feature against a local copy of the app built from commit `a84e81254b34ff62b0e76639b4393fde498ba37e`.

DoubtQueue is released under the [MIT License](https://github.com/NxtLabTech/DoubtQueue/blob/main/LICENSE).

Copyright (c) 2026 NxtLabTech
:::

# DoubtQueue README Features section

**Pull request:** [#53, Add Features section to README](https://github.com/NxtLabTech/DoubtQueue/pull/53)
**Status:** Open, submitted October 8, 2026.

## The problem

The DoubtQueue README explained how to install and run the app, but not what the app could do. A contributor could not see which features existed before choosing an issue to work on.

Issue #30 asked for a short Features section, in simple English, with two lists, one for students and one for mentors. It had five acceptance criteria:

- The README has a Features section with Students and Mentors lists.
- Each listed feature exists in the current app.
- The 10-second refresh and the confirmation dialogs are mentioned.
- The section is short, about 20 lines or fewer, and uses simple English.
- Existing README sections are unchanged.

## How I checked each line

The issue said to run the app and check every sentence before writing it. I ran the backend and the Flutter app locally and used both sides of the app in the browser, one tab as a student and one as a mentor.

| Feature | How I checked it |
| --- | --- |
| Search, filter, and sort sessions | Used each control on the session list and recorded the exact labels. |
| Join a queue | Filled in the join form and recorded its four fields. |
| Position and students ahead | Read the screen after joining. |
| 10-second refresh | Watched the doubt screen for the refresh indicator, then used the mentor tab to change a doubt's status and watched the student screen update without a click. |
| Statistics, take next, solve, skip | Used each control on the mentor dashboard and watched both screens change. |
| Confirmation dialogs | Opened the Skip and Close session dialogs and cancelled them. I confirmed Mark solved has no dialog. |
| Start a session | Created a session and confirmed it was selected and listed. |

I used the on-screen wording in the README. For example, the button is called **Mark solved**, not "Solve".

## The section I submitted

````markdown
## Features

There is no login. Anyone can open the app as a student or a mentor.

**Students**

- Search sessions by session or mentor name.
- Filter sessions by Open, Closed or All, and sort them by Newest or Most waiting.
- Join a session queue with a name, email, topic and question.
- See your position in the queue and how many students are ahead of you.
- The doubt screen refreshes every 10 seconds, so you see when it is your turn and when your doubt is solved or skipped.

**Mentors**

- Start a session with a title and a mentor name, or select an open session.
- See statistics for waiting, in progress, solved and skipped doubts.
- Take the next student, then mark the doubt as solved or skip it.
- Confirm before you skip a doubt or close a session.
- Close a session so no more students can join.
````

The section is 14 lines of text and sits between the introduction and the Technology section. No existing README text was changed. The diff was 20 insertions and 0 deletions.

## What I noticed

- The dropdown for selecting a session lists only open sessions. A closed session disappears from it, so the README says "select an open session".
- A newly created session appears in the student list only after a manual refresh. The README claims automatic refresh only for the doubt screen, so the text stays accurate.
- The README introduction already says there is no login, and the new section repeats it because the issue asked for that mention. I left the introduction alone to keep the change inside the issue's scope, and noted the overlap in the pull request.

## What I did not test

The change only edits documentation, so I did not run the backend or app test suites.

## Tools and environment

Flutter 3.47.6 and PHP 8.5.4 on Ubuntu 26.04.1 under WSL2, with the app opened in a Windows browser through `flutter run -d web-server`.