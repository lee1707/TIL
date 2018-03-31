# Today I learned

I went seminar today. It held at Ebrain(seonjeongleung, Seoul, Korea).

I learned **uftrace**(opensource) and how to use github(and sourcetree)
also Emoji :smile:


# uftrace
[uftrace](https://github.com/namhyung/uftrace)

uftrace is opensource that you can use in Linux kernel.
It helps us to trace c/c++ function. 

# This is how to use uftrace in Linux
```
#Ubuntu
$sudo apt-get install libelf-dev

#Fedora, RHEL
$ sudo dnf install elfutils-libelf-devel

$git clone https://github.com/namhyung/uftrace.git

$cd uftrace

$./configure

$make

$sudo make install 

$cd tests

$ls s-*

$gcc -o t -fibonacci -s -fibonacci.c

$gcc -o -pg t -fibonacci -s -fibonacci.c

$uftrace record t -finonacci 5

$uftrace replace
```

Lecturer also told us there are many great lecture held by The Linux Foundation.
[Linux Foundation](http://www.linuxfoundation.org)

He said **The main points of opensource are review and debate** 

He told us to look at **Todo** and **contributing.md** at opensouce link above(uftrace).

# github
Junyoung was lecturer. :thumbsup:

I learned how to create branch and merge in sourcetree.

It was training lectruer. We spend time to follow his lectruer and learned a lot. 

