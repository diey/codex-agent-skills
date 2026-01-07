# Examples: Minimal File Changes

## Example 1: Correct usage (edit existing file)

User:
"Add a new status badge to the user listing."

Correct response:

- Modify the existing Blade / Livewire file where the listing already exists
- Reuse existing styles or Flux UI components
- Do NOT create a new component or helper

Why this is correct:

- Change is local
- No new abstraction is required
- Existing structure already supports the change

---

## Example 2: Incorrect usage (unnecessary file explosion)

User:
"Refactor this controller method to be cleaner."

Incorrect response:

- Creating a new `Services/UserService.php`
- Extracting logic into multiple helper classes
- Introducing a new base abstraction

Why this is wrong:

- User did not ask for architectural changes
- Refactor can be done safely within the existing file
- Adds maintenance and cognitive overhead

---

## Example 3: New file required by Laravel convention

User:
"Add validation for this form."

Correct response:

- Create a new Form Request class using Laravel conventions
- Update the controller or Livewire component to use it
- Stop and ask before creating any additional files

Why this is correct:

- Laravel conventions explicitly encourage Form Requests
- Exactly one new file is created
- Scope is controlled

---

## Example 4: Separation requires approval

User:
"This method is getting large."

Correct response:
"This can be cleaned up locally, or we can extract it into a separate class.
I recommend a local refactor first. Let me know if you want me to extract it."

Why this is correct:

- Minimal-change option is offered first
- Larger refactor is proposed, not assumed
