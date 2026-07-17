# su26-ai301-contribution

# Contribution [#]: Improve accessibility and styles for event form when editing with keyboard [#1060]


**Contribution Number:** 1 
**Student:** Wany Muhimuzi  
**Issue:** https://github.com/SwitchbackTech/compass-calendar/issues/1060
**Status:** [Phase III]

---

## Why I Chose This Issue
I chose this issue because I wanted to gain more experience with frontend development and accessibility. Although I have worked on frontend projects before, I wanted to deepen my understanding of how keyboard interactions and user interface accessibility are implemented in a larger open-source project.  
1. I've worked on frontend work before but not as much as I wanted to do. I want to work on frontend work before I move over to backend to slowly work bring me to working through harder issues.
2. There is a paper trail about the issue, so if I have questions, I can also go back and look at issues related to the one I am working on.

From reading, my main goal is to help improve the quality of the user interface in regards to adding an event to the calender.

---

## Understanding the Issue

### Problem Description
The primary goal of this issue is to improve keyboard accessibility within the event creation form. Users should be able to navigate the form using only the keyboard, clearly identify which element currently has focus, and complete the entire event creation process without relying on a mouse.

### Expected Behavior

TUsers can navigate to the event title and title the event, select a event type, pick a timefrem for the event, and then save. It will later show in teh calender within that time frame.

### Current Behavior

[Users can navigate to the event title, but keyboard navigation does not fully support selecting an event type, interacting with other controls, or completing the save process efficiently]

### Affected Components

[PrioritySection.tsx EventTypeSection.tsx
EventForm.tsx and SaveSection.tsx]

---

## Reproduction Process

### Environment Setup
Using the project's README.md via GitHub, I was able to set up the environment. One issue is that a package called Bun was used, and it is not commonly used among college students.

Working branch: https://github.com/WanyGM/compass-calendar/tree/fix-issue-1060

### Steps to Reproduce

1. Navigate to https://compasscalendar.com/ or local host  http://localhost:9080
2. Click a time in the day schedule
3. Using the Tab key, navigate through the process to add an event as you look at what is highlighted
4. **Expected:** User will navigate through Title, Event Type, Time (start and End), Repeat, Description, Save and then repeat
5. 5. **Actual:** After the user gets to Save, what is highlighted is no longer visible; it is not keyboard-friendly.

### Reproduction Evidence

- **Commit showing reproduction:** https://github.com/WanyGM/compass-calendar/tree/fix-issue-1060
- **Screenshots/logs:** 

https://github.com/user-attachments/assets/b1271576-b539-4d7a-9eea-6bd3a47ecb24


- **My findings:** When navigating with only the keyboard, the event creation form does not maintain a clearly visible focus state after saving. This makes it unclear where the user is on the page after the action completes.]

---

## Solution Approach

### Analysis
When navigating with only the keyboard, the event creation form does not maintain a clearly visible focus state after saving. This makes it unclear where the user is on the page after the action completes. This makes the interface confusing for keyboard-only users because they lose track of where they are in the form if they are not ready to save and want to return to the title to make any changes.

### Proposed Solution

After an event is being created but changes need to be changed, focus should be moved to a predictable and visible element, such as the event title field or another appropriate part of the event form and also the ablity to check enter for make selection for event type, time, repeat and save.

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** Keyboard users should be able to complete the entire event creation process without using a mouse
**Match:** There are shortcuts to navigate the website if the the "?" key to open the shortcuts

**Plan:** 
1.Locate the components responsible for Event Type, Time, Repeat, and Save.
2.Ensure each control can be activated using the Enter key in addition to mouse interaction.
3.Update focus management so that focus remains visible and moves to a logical location after saving or going back to make changes.
4.Verify that keyboard navigation using Tab and Enter behaves consistently across the event form.

**Implement:** https://github.com/WanyGM/compass-calendar/tree/fix-issue-1060

**Review:** 
Commit 4 hours / week for a minimum of six months
Respond to our internal chats within 24 hours M-F.

**Evaluate:** Going through the process of creating an event without using my mouse or my touchscreen to ensure smooth navigation through the event form.

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Test that the Event Type control can be selected using the Enter key]
- [ ] Test case 2: [Test that the Repeat control can be selected using the Enter key]
- [ ] Test case 3: [Test that the Save button can be selected using the Enter key]

### Integration Tests

- [ ] Test that a user can navigate through the event form using only the keyboard.
- [ ] Test that focus remains visible after saving an event.

### Manual Testing

[The event form can be navigated with the Tab key.
I started fixing keyboard selection for Event Type and Repeat.
Some repeat selection behavior still needs additional work.
After saving, focus still needs to be checked to make sure it remains visible and predictable.]

---

## Implementation Notes

### Week [June 18 - 25, 2026] Progress

[What I worked on:
Set up and reviewed the event form code.
Worked on fixing keyboard selection for the Event Type control.
Started working on keyboard selection for the Repeat control.
Reviewed how the form handles Tab navigation, Enter selection, and the Save action.

Challenges faced:
The project uses Bun, so I had to become familiar with that setup.
While preparing to push my changes, I realized I needed to run git pull. So before pushing, I stashed my branch and did a git pull.
After pulling the latest changes, it looked like some of my local work may have been removed or overwritten.
I need to confirm whether the work was deleted, merged, or recoverable through Git history.
]

### Week [June 26 - July 1, 2026] Progress

[What I worked on : 
]Re-evaluated my initial implementation and decided that removing the changes was the best course of action. Although the code worked to some extent, it did not function the way I wanted or provide the user experience I was aiming for.
The time spent on the initial implementation gave me a much better understanding of the repository structure and helped me identify which files and components would need to be modified if I decide to revisit this approach later.
Created a dummy account so I could explore the application with full access to the event creation and management features. This provided a better understanding of how the event workflow is intended to function and gave me additional context for the accessibility improvements.
Continued reviewing the event form and keyboard interactions to better understand the existing implementation before making further changes.

Challenges faced:
One challenge was recognizing when it was better to step back rather than continue building on an approach that was not meeting my goals. Although deleting my changes was disappointing, it was the right decision and prevented me from adding unnecessary complexity.
I also realized that taking a break from the project was necessary. During that time, the repository continued to receive updates, which meant I needed to revisit the application with a fresh perspective and account for changes that had been made since I last worked on it.

### Week [July 1 - July 5, 2026] Progress
[What I worked on : 
Continued implementing keyboard accessibility improvements for the event creation form.
Updated the keyboard navigation so users can tab through the event panel using the Tab key.
Implemented keyboard navigation for the Event Type selector. Once the selector has focus, users can now use the Left and Right Arrow keys to move between the available event types without using a mouse.
Tested the new keyboard behavior to ensure the navigation worked as expected while moving through the event form.
Continued reviewing the remaining controls to identify where similar keyboard support should be added.
Challenges faced:
One challenge was determining the most intuitive keyboard interactions for the event form while keeping the behavior consistent with the rest of the application.
I spent time understanding how the event components manage focus and keyboard events before making changes.
Although the Event Type selector is now keyboard accessible, additional work is still needed to provide similar functionality for the remaining controls, such as Repeat, Time, and the focus behavior after saving an event.

### Code Changes

- **Files modified:** [SaveSection.tsx, PrioritySection.tsx]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [My primary focus was to ensure that users could continue navigating the event panel using the Tab key while adding keyboard support for the Event Type selector. I chose to use the Left and Right Arrow keys for selecting event types because this interaction is intuitive for navigating between multiple options. I also plan to make these keyboard shortcuts more discoverable by displaying them either near the Event Type section or within the existing keyboard shortcuts panel.]

---

## Pull Request


**PR Description:** [https://github.com/SwitchbackTech/compass-calendar/pull/1968]

**Maintainer Feedback:**
- [July 8th]: [They had thank me for my time but my PR did meet the requirement for new contributors]
- [July 11]: [I gave it a thumbs, because following the message the issue was closed ]

**Status:** [Reviewed ]

---

## Learnings & Reflections

### Technical Skills Gained

[Throughout this contribution, I learned how to use AI more effectively when working on projects that I was unfamiliar with. Instead of expecting AI to provide complete solutions, I learned how to ask better questions, use it to understand unfamiliar code, and verify my own ideas. I also gained experience working with new development tools, particularly Bun, which was my first time using an alternative JavaScript runtime and package manager. Learning how Bun fits into the project's development workflow helped me become more comfortable adapting to new technologies.]

### Challenges Overcome

[One of the biggest challenges I faced was learning when and how to rely on AI. At first, I found it difficult to know when to trust AI's suggestions because I was still trying to understand the project's codebase. Rather than continuing to make changes that I didn't fully understand, I decided to slow down and focus on learning how the project worked first. I spent time understanding Bun, the project structure, and how the different components interacted before continuing development. This approach helped me build confidence and gave me a much stronger understanding of the repository. By the end of this contribution, I was using AI as a learning tool and a guide instead of depending on it to solve problems for me.]

### What I'd Do Differently Next Time

[If I were to start another open-source contribution, I would spend more time reading the project's CONTRIBUTING.md before writing any code. Although solving the technical problem is important, the contribution guidelines often provide valuable information about the project's expectations, coding standards, and workflow. Understanding those requirements earlier would have helped me plan my work more effectively and avoid spending time on approaches that did not align with the maintainers' expectations.]

---

## Resources Used

- [Bun.com]
- [https://pyk.sh/cookbooks/typescript/how-to-listen-for-keyboard-shortcuts]

