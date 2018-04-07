# Today I learned
ListIterator, 

* ListIterator<T> it = list.listIterator();

while (it.hasNext()) {
  T t = it.next();
  T prev = it.previous();
}

[reference](https://stackoverflow.com/questions/19850468/how-can-i-access-the-previous-next-element-in-an-arraylist)
