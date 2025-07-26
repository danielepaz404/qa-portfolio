# To Do List [Manual Testing Study]

<details>

<summary>Table of Contents</summary>
    
- [Test Plan](#test-plan)
- [Features Identified](#features-identified)
- [Test Case Overview](#test-case-overview)
- [Test Cases](#test-cases)
    - [TDL#01 – Create todos](#tdl01--create-todos)
    - [TDL#02 – Edit a todo](#tdl02--edit-a-todo)
    - [TDL#03 – Delete a todo](#tdl03--delete-a-todo)
    - [TDL#04 – Filter todo list by active](#tdl04--filter-todo-list-by-active)
    - [TDL#05 – Filter todo list by completed](#tdl05--filter-todo-list-by-completed)
    - [TDL#06 – Item counter displays correct number of active items when there's only one active item](#tdl06--item-counter-displays-correct-number-of-active-items-when-theres-only-one-active-item)
    - [TDL#07 – Item counter displays correct number of active items when there's multiple active items](#tdl07--item-counter-displays-correct-number-of-active-items-when-theres-multiple-active-items)
    - [TDL#08 – Item counter displays correct number of active items when there are active and completed todos](#tdl08--item-counter-displays-correct-number-of-active-items-when-there-are-active-and-completed-todos)
    - [TDL#09 – Item counter displays correct number of active items when there are only completed todos](#tdl09--item-counter-displays-correct-number-of-active-items-when-there-are-only-completed-todos)
    - [TDL#10 – Clear the todo list](#tdl10--clear-the-todo-list)
    - [TDL#11 – Set all todos as completed through batch action](#tdl11--set-all-todos-as-completed-through-batch-action)
- [Bug Reports](#bug-reports)
    - [BUG#01 – Debug text visible on hover of delete icon](#bug01--debug-text-visible-on-hover-of-delete-icon)
    - [BUG#02 – Item counter shows wrong number of active elements](#bug02--item-counter-shows-wrong-number-of-active-elements)
    - [BUG#03 – Batch toggle button needs two clicks to work when all todos are completed](#bug03--batch-toggle-button-needs-two-clicks-to-work-when-all-todos-are-completed)
    - [BUG#04 – Icon for batch toggle button is misleading](#bug04--icon-for-batch-toggle-button-is-misleading)

</details>

---

## Test Plan

- Goals
    - Test the core functionalities of the [TodoList](https://todolist.james.am/#/) website.
- Techniques
    - Exploratory testing
    - Black-box testing
- Activities
    - Identify possible requirements through exploratory testing
    - Write test cases for the main features/user journeys
    - Start black-box testing by following test cases
    - Create bug reports for any issue found
- Expected Outputs
    - A list of core features
    - Test cases for black-box testing
    - Bug report if any bugs were found

---

## Features Identified
- Todo Creation
- Todo Editing
- Todo Deletion
- Filtering
- Item Counter
- Clear All
- Batch Completion Toggle

---


## Test Case Overview

| ID     | Title                                                              | Feature       | Status | Related Bugs |
|--------|--------------------------------------------------------------------|---------------|--------|--------------|
| TDL#01 | Create todo                                                        | Todo Creation | Pass   |              |
| TDL#02 | Edit a todo                                                        | Todo Editing  | Pass   |              |
| TDL#03 | Delete a todo                                                      | Todo Deletion | Fail   | BUG#01       |
| TDL#04 | Filter todo list by active                                         | Filtering     | Pass   |              |
| TDL#05 | Filter todo list by completed                                      | Filtering     | Pass   |              |
| TDL#06 | Item counter shows "1 item left" (1 active todo)                   | Item Counter  | Fail   | BUG#02       |
| TDL#07 | Item counter shows "2 items left" (2 active todos)                 | Item Counter  | Fail   | BUG#02       |
| TDL#08 | Item counter shows "1 item left" (1 active todo, 1 completed todo) | Item Counter  | Fail   | BUG#02       |
| TDL#09 | Item counter shows "0 items left" (2 completed todos)              | Item Counter  | Fail   | BUG#02       |
| TDL#10 | Clear the todo list                                                | Clear All     | Pass   |              |
| TDL#11 | Set all todos as completed through batch action                    | Batch Toggle  | Fail   | BUG#04       |

---


## Test Cases

### TDL#01 – Create todos
**Feature:** Todo Creation  
**Preconditions:** App is loaded and user is on the main page  
**Test Data:** Any string

| Step | Action      | Expected Result                                                                |
|------|-------------|--------------------------------------------------------------------------------|
| 1    | Insert text | The input should accept the text with no errors                                |
| 2    | Press Enter | A new todo with the specified text should be created and displayed in the list |

**Status:** Pass 

---

### TDL#02 – Edit a todo  
**Feature:** Todo Editing  
**Preconditions:** A todo exists in the list  
**Test Data:** Different text than the existing one

| Step | Action                | Expected Result                                                                       |
|------|-----------------------|---------------------------------------------------------------------------------------|
| 1    | Double click the todo | Element should change to an input box with the todo text                              |
| 2    | Modify text           | Current text should change according to what is input                                 |
| 3    | Press Enter           | Input should change to a read-only text element with same content as specified before |

**Status:**  Pass

---

### TDL#03 – Delete a todo  
**Feature:** Todo Deletion  
**Preconditions:** A todo exists in the list

| Step | Action           | Expected Result                  |
|------|------------------|----------------------------------|
| 1    | Hover the todo   | Should display a cross sign icon |
| 2    | Click cross icon | Todo should no longer be visible |

**Status:** Pass  
**Related Bugs:** BUG#01

---

### TDL#04 – Filter todo list by active  
**Feature:** Filtering  
**Preconditions:** At least 1 completed and 1 active todo; active filter is visible

| Step | Action              | Expected Result                      |
|------|---------------------|--------------------------------------|
| 1    | Click active filter | Should display only the active todos |

**Status:** Pass  

---

### TDL#05 – Filter todo list by completed  
**Feature:** Filtering  
**Preconditions:** At least 1 completed and 1 active todo; completed filter is visible

| Step | Action                 | Expected Result                         |
|------|------------------------|-----------------------------------------|
| 1    | Click completed filter | Should display only the completed todos |

**Status:** Pass

---

### TDL#06 – Item counter displays correct number of active items when there's only one active item
**Feature:** Item Counter  
**Preconditions:** List has 1 active todo

| Step | Action                  | Expected Result                       |
|------|-------------------------|---------------------------------------|
| 1    | Locate the item counter | Should display the text "1 item left" |

**Status:** Fail  
**Related Bugs:** BUG#02

---

### TDL#07 – Item counter displays correct number of active items when there's multiple active items
**Feature:** Item Counter  
**Preconditions:** List has 2 active todos 

| Step | Action                  | Expected Result                        |
|------|-------------------------|----------------------------------------|
| 1    | Locate the item counter | Should display the text "2 items left" |

**Status:** Fail  
**Related Bugs:** BUG#02

---

### TDL#08 – Item counter displays correct number of active items when there are active and completed todos
**Feature:** Item Counter  
**Preconditions:** List has 1 active, 1 completed 

| Step | Action                  | Expected Result                       |
|------|-------------------------|---------------------------------------|
| 1    | Locate the item counter | Should display the text "1 item left" |

**Status:** Fail  
**Related Bugs:** BUG#02

---

### TDL#09 – Item counter displays correct number of active items when there are only completed todos
**Feature:** Item Counter  
**Preconditions:** List has 2 completed todos

| Step | Action                  | Expected Result                        |
|------|-------------------------|----------------------------------------|
| 1    | Locate the item counter | Should display the text "0 items left" |

**Status:** Fail  
**Related Bugs:** BUG#02

---

### TDL#10 – Clear the todo list  
**Feature:** Clear All  
**Preconditions:** At least one completed todo exists; clear button is visible

| Step | Action             | Expected Result                         |
|------|--------------------|-----------------------------------------|
| 1    | Click clear button | List should delete only completed todos |

**Status:** Pass  

---

### TDL#11 – Set all todos as completed through batch action  
**Feature:** Batch Completion Toggle  
**Preconditions:** List has 2 active todos

| Step | Action                    | Expected Result                      |
|------|---------------------------|--------------------------------------|
| 1    | Click batch action button | All todos should become completed    |
| 2    | Click batch action again  | All todos should become active again |

**Status:** Fail  
**Related Bugs:** BUG#04

---

## Bug Reports

### BUG#01 – Debug text visible on hover of delete icon
**Feature:** Todo Deletion  
**Found During:** TDL#03 – Delete a todo  
**Steps to Reproduce:**
1. Create a todo
2. Hover the delete icon

**Expected:** User friendly text or no text at all  
**Actual:** Text "TODO:REMOVE THIS EVENTUALLY" 
**Priority:** Medium 
**Severity:** Low  
**Status:** Open  

---

### BUG#02 – Item counter shows wrong number of active elements
**Feature:** Item Counter  
**Found During:** TDL#06 – Item counter shows "1 item left" (1 active todo)  
**Steps to Reproduce:**
1. Create a todo if there's none
2. Locate item counter and verify its value

**Expected:** Counter displays correct total count of items  
**Actual:** Counter is off by 1 
**Priority:** Medium
**Severity:** Medium  
**Affects:** TDL#06, TDL#07, TDL#08, TDL#09  
**Status:** Open  

---

### BUG#03 – Batch toggle button needs two clicks to work when all todos are completed
**Feature:** Batch Toggle  
**Found During:** TDL#11 – Set all todos as completed through batch action   
**Steps to Reproduce:**
1. All todos should be completed
2. Click batch toggle button
3. Click batch toggle button again

**Expected:** Should toggle todos status when clicking the batch toggle button once  
**Actual:** Batch toggle button needs two clicks to work properly  
**Priority:** Medium 
**Severity:** Medium  
**Status:** Open  

---

### BUG#04 – Icon for batch toggle button is misleading
**Feature:**  Batch Toggle
**Found During:** TDL#11 – Set all todos as completed through batch action   
**Steps to Reproduce:**
1. Have at least one todo
2. Observe the batch toggle button

**Expected:** Icon should clearly represent the button's action to check/uncheck todos  
**Actual:** Current icon represents a dropdown behavior to expand  
**Priority:** Low 
**Severity:** Low  
**Status:** Open  

