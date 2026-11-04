
# Power Fx Examples for Canvas Apps

This guide contains beginner-friendly Power Fx examples for Microsoft Power Apps Canvas Apps.

## 1. Display a Welcome Message

**Control:** Label  
**Property:** Text

```powerfx
"Welcome to Power Apps!"
```

## 2. Validate a Required Text Input

**Control:** Submit button  
**Property:** DisplayMode

```powerfx
If(
    IsBlank(Trim(txtName.Text)),
    DisplayMode.Disabled,
    DisplayMode.Edit
)
```

This disables the button when the name input is empty.

## 3. Search a Gallery

**Control:** Gallery  
**Property:** Items

Assumption: the app contains a data source named `Employees` with a `FullName` column and a text input named `txtSearch`.

```powerfx
Filter(
    Employees,
    StartsWith(FullName, txtSearch.Text)
)
```

## 4. Set a Variable

**Control:** Button  
**Property:** OnSelect

```powerfx
Set(varWelcome, "Hello, team!")
```

A label can display the variable using:

```powerfx
varWelcome
```

## 5. Show a Success Notification

**Control:** Button  
**Property:** OnSelect

```powerfx
Notify(
    "Record saved successfully",
    NotificationType.Success
)
```

## 6. Handle Errors When Saving

Example pattern for a form named `frmEmployee`:

```powerfx
IfError(
    SubmitForm(frmEmployee),
    Notify(
        "Unable to submit the form",
        NotificationType.Error
    )
)
```

Check the form's validation and data-source configuration before using this example.

## Notes

- Control and data-source names must match the actual app.
- Formula argument separators may vary with regional settings.
- Test examples in a development environment before using them in production.
- These examples are learning references, not a complete production solution.
