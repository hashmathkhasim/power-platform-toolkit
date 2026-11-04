
# Power Platform Toolkit — Test Plan

## Purpose

This document records the checks needed to validate the Power Fx examples in a Microsoft Power Apps Canvas App.

## Current validation status

- [x] Documentation structure created.
- [ ] Formulas checked in a live Power Apps environment.
- [ ] All test cases executed.
- [ ] Results and screenshots recorded.

The examples must not be described as runtime-tested until the checks below have actually been completed.

## Test cases

### 1. Welcome message

**Formula:** `"Welcome to Power Apps!"`

- Add a Label control.
- Set its Text property to the formula.
- Expected result: the label displays the welcome message.

### 2. Required input validation

**Formula under review:** `If(IsBlank(Trim(txtName.Text)), DisplayMode.Disabled, DisplayMode.Edit)`

- Add a Text input named `txtName` and a Button.
- Set the Button's DisplayMode property to the formula.
- Test with an empty input, spaces only, and a non-empty name.
- Expected result: the button is disabled for blank or whitespace-only input and enabled for a name.

### 3. Gallery search

- Connect a sample data source named `Employees`.
- Ensure it has a text column named `FullName`.
- Set a Gallery's Items property to the documented search formula.
- Test a matching name, a partial name, and a term with no matches.
- Record the observed results and any delegation warnings.

### 4. Variable

- Set a Button's OnSelect property to `Set(varWelcome, "Hello, team!")`.
- Set a Label's Text property to `varWelcome`.
- Select the button.
- Expected result: the label displays `Hello, team!`.

### 5. Notification

- Set a Button's OnSelect property to the documented `Notify` formula.
- Select the button.
- Expected result: a success notification appears.

## Results log

| Date | Test | Result | Notes |
|---|---|---|---|
| Not run | Welcome message | Pending | Requires Power Apps |
| Not run | Input validation | Pending | Requires Power Apps |
| Not run | Gallery search | Pending | Requires sample data source |
| Not run | Variable | Pending | Requires Power Apps |
| Not run | Notification | Pending | Requires Power Apps |

## Official references

- Power Fx formula reference: https://learn.microsoft.com/en-us/power-platform/power-fx/formula-reference-canvas-apps
- Power Fx error handling: https://learn.microsoft.com/en-us/power-platform/power-fx/error-handling
