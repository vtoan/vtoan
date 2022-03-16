## Table of Contents
- [1. Key concepts](#1-key-concepts)
- [2. Approach](#2-approach)
- [3. Common form classes](#3-common-form-classes)
- [4. Setting up the form model](#4-setting-up-the-form-model)
- [5. Mutability of the data model](#5-mutability-of-the-data-model)
---

# 1. Key concepts
- **Form model**: track value changes between the form input elements that users interact with and the form data in your component model).
- **Data flow**: to keep the view in sync with the component model and the component model in sync with the view.
- **Form validation**.

# 2. Approach
Tow approach:
  - Reactive form.
  - Template-driven form.

Differences:

|                         | REACTIVE                             | TEMPLATE                        |
| ----------------------- | ------------------------------------ | ------------------------------- |
| **Setup of form model** | Explicit, created in component class | Implicit, created by directives |
| **Data model**          | Structure, immutable                 | Unstructured, mutable           |
| **Data flow**           | Synchronous                          | Asynchronous                    |
| **Form validation**     | Functions                            | Directives                      |

# 3. Common form classes
- `FormControl`: tracks value and validation status of an individual form control.
- `FormGroup`: tracks the same values and status for a collection of form controls (with key as `string`).
- `FormArray`: tracks the same values and status for a array of form controls (with no key).
- `ControlValueAccessor`: create a bridge between Angular `FormControl` instances and built-in `DOM elements`.

# 4. Setting up the form model
**Reactive Form**

- *Setup*:

  - Define **the form model** (`FormControl` instance) in the component class.
  - Links **the form model** (`FormControl` instance) to **a specific form element** in view by using `[formControl]` directive.

*<u>Note</u>*: **The form model** is the source of truth.

- *Data flow*:

In reactive forms, each form element in view directly linked to the form model (`FormControl` instance).

Updates from the **view to the model** and from **the model to the view** are synchronous and do not depend on how the UI is rendered.

Read details [here](https://angular.io/guide/forms-overview#data-flow-in-reactive-forms).


**Template Driven From**

- *Setup*: Using `NgModel` directive.

In template-driven form, the **form model** is implicit. The directive `NgModel` creates and manages a `FormControl` instance for a given form element.

*<u>Note</u>*: **The template** is the source of truth. You **do not have direct programmatic access** to the `FormControl` instance.

- *Data flow*:

In template-driven forms, each form element is linked to a directive that **manages the form model internally**.

Read details [here](https://angular.io/guide/forms-overview#data-flow-in-template-driven-forms).

# 5. Mutability of the data model
- With reactive forms, the `FormControl` instance always **returns a new value** when the control's value is updated.

- With template-driven forms, the value of property is always **modified** to its new value.

Read details [here](https://angular.io/guide/forms-overview#mutability-of-the-data-model).