# su26-ai301-contribution

# Contribution [#]: Improve accessibility and styles for event form when editing with keyboard [#1060]


**Contribution Number:** 1 
**Student:** Wany Muhimuzi  
**Issue:** https://github.com/SwitchbackTech/compass-calendar/issues/1060
**Status:** [Phase II ]

---

## Why I Chose This Issue
In the past, I've worked on frontend work, and I enjoyed. One thing I wish I had more time to work on is working with different types of elements, as we only had 3 months to build a website from complete scratch, including blueprinting  
1. I've worked on frontend work before but not as much as I wanted to do. I want to work on frontend work before I move over to backend to slowly work bring me to working through harder issues.
2. There is a paper trail about the issue, so if I have questions, I can also go back and look at issues related to the one I am working on.

From reading, my main goal is to help improve the quality of the user interface in regards to adding an event to the calender.

---

## Understanding the Issue

### Problem Description

The issue  is to improve the user's ability to edit any events that are in their calendar while staying in the flow

### Expected Behavior


Because it is a style change, what needs to happen is that when adding an event, a window will pop up and look different from the rest of the page without looking too distracted

### Current Behavior

[What actually happens?]

### Affected Components

[Which parts of the codebase are involved?]

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

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
