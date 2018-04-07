# Today I learned
ListIterator, html placeholder

# ListIterator<T> it = list.listIterator();

```
while (it.hasNext()) {
  T t = it.next();
  T prev = it.previous();
}
```
**next <-> previous**

reference: [stackoverflow](https://stackoverflow.com/questions/19850468/how-can-i-access-the-previous-next-element-in-an-arraylist)

# HTML5 textarea placeholder not appearing
=> Gatcha, change placing
```
Good:

    <textarea></textarea>
Bad:

    <textarea>
    </textarea>
```

reference: [stackoverflow](https://stackoverflow.com/questions/10186913/html5-textarea-placeholder-not-appearing)

# Multiple radio button groups in one form

```
<form>
    <fieldset id="group1">
        <input type="radio" value="">
        <input type="radio" value="">
    </fieldset>

    <fieldset id="group2">
        <input type="radio" value="">
        <input type="radio" value="">
        <input type="radio" value="">
    </fieldset>
</form>
```
reference: [stackoverflow](https://stackoverflow.com/questions/28543752/multiple-radio-button-groups-in-one-form?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa)

