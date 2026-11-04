
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
Filter(
    Employees,
    StartsWith(FullName, txtSearch.Text)
)
### Search behaviour and limitations

The `StartsWith` function matches text at the beginning of the specified column. It does not search for text appearing only in the middle of a name.

Example, for `FullName = "Mohammed Hashmath"`:

- Search for `Moh` — matches.
- Search for `Hash` — does not match.
- An empty search input may return all records because `StartsWith` matches an empty prefix.

### Delegation considerations

Delegation support depends on the connected data source. Check Power Apps Studio for delegation warnings and verify that the formula retrieves the expected records for the intended data volume.

### Validation status

This example has been reviewed against the official Power Fx documentation but has not yet been runtime-tested in Power Apps.


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

---

## Official Microsoft References

Use these official resources to verify Power Fx formulas and understand delegation behaviour.

- [StartsWith function](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-startswith)
- [Filter and Search functions](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-filter-lookup)
- [Delegation overview](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/delegation-overview)

### Verification notes

- Confirm function syntax and argument names against the official documentation.
- Check delegation support for the specific connected data source.
- Runtime validation of the examples is pending until they are tested in Power Apps Studio.

Check the form's validation and data-source configuration before using this example.

## Notes

- Control and data-source names must match the actual app.
- Formula argument separators may vary with regional settings.
- Test examples in a development environment before using them in production.
- These examples are learning references, not a complete production solution.
