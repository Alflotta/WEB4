Task 3. Problems in the café form

1. Line: <input type="text" placeholder="Your name">
Problem: No label. The placeholder disappears when the user types, and a screen reader does not know what the field is.
Fix: Added <label for="name"> and id="name".

2. Line: <input type="text" placeholder="Email">
Problem: Wrong type: the phone keyboard has no @ and the browser does not check the address. No label.
Fix: type="email", a label and autocomplete="email".

3. Line: <label>Phone</label>
Problem: The label has no "for", so a click on it does not focus the field and a screen reader does not connect them.
Fix: Added for="phone".

4. Line: <input type="text" id="phone">
Problem: A text keyboard is shown on a phone and there is no name, so the value is never sent.
Fix: type="tel", name="phone", autocomplete="tel".

5. Line: <label for="guests"> and <input id="people">
Problem: for and id do not match, so the label is connected to nothing.
Fix: Both use the same id: "guests".

6. Line: <input type="text" id="people">
Problem: The user can type letters or a negative number. There is no name, so the data is not sent.
Fix: type="number", min="1", max="20", name="guests".

7. Line: <input type="text" id="date" placeholder="dd/mm/yyyy">
Problem: The user has to guess the format, it is easy to make a mistake and there is no calendar.
Fix: type="date" with name="date".

8. Line: <input type="radio" name="inside" id="date">
Problem: Duplicate id="date": the Date label can focus the wrong element and the HTML is invalid.
Fix: Unique ids: seating-inside and seating-terrace.

9. Line: name="inside" and name="terrace"
Problem: The radios have different names, so they are not one group: both can be selected and the arrow keys do not switch between them.
Fix: One shared name="seating" with value="inside" and value="terrace".

10. Line: <input type="radio"> Inside
Problem: The text is not a label: the click area is tiny and a screen reader does not read the option name.
Fix: Each option is in a form-check block with <label for>.

11. Line: <p>Seating:</p>
Problem: A screen reader does not announce it as the title of the radio group.
Fix: <fieldset> with <legend>.

12. Line: <select>
Problem: No label and no name: the choice between Lunch and Dinner is not described and is never sent.
Fix: Added <label for="meal">, id, name="meal" and option values.

13. Line: <textarea placeholder="Comments">
Problem: A placeholder is used instead of a label and there is no name, so the comment is lost.
Fix: Added a label, id and name="comments".

14. Line: <input type="checkbox"> I agree to the terms
Problem: The text is not linked to the checkbox, there is no name, and the agreement is not required.
Fix: <label for="terms">, name and required.

15. Line: <div class="btn btn-primary">Reserve</div>
Problem: A div cannot be reached with Tab, cannot be pressed with Enter or Space and does not submit the form.
Fix: <button type="submit">.

16. Line: <form>
Problem: No action and method, and no required fields, so an empty reservation can be sent.
Fix: action="#", method="post" and required on the needed fields.

Another possible fix for problem 1 (no label)
I could use aria-label="Your name" instead of a visible label. I chose the visible label because it stays on the screen while the user types, it makes the click area bigger and it helps all users, not only screen reader users. An aria-label is invisible, so a sighted user would see an unnamed field again.

Another possible fix for problem 15 (div as a button)
I could keep the div and add role="button", tabindex="0" and JavaScript for Enter, Space and form submission. I chose <button type="submit"> because the browser already gives focus, keyboard activation and form submission, and JavaScript is not allowed in this assignment.
