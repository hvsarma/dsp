# Learn command line

Please follow and complete the free online [Command Line Crash Course
tutorial](http://cli.learncodethehardway.org/book/). This is a great,
quick tutorial. Each "chapter" focuses on a command. Type the commands
you see in the _Do This_ section, and read the _You Learned This_
section. Move on to the next chapter. You should be able to go through
these in a couple of hours.


---

Make a cheat sheet for yourself: a list of commands and what they do, focused on things that are new, interesting, or otherwise worth remembering.

> My pocket-list of "mostly-used" CL commands: ```cd, pwd, echo, cat, vi, >, |, less, more, python```

> My pocket-list of "occasionally-used" CL commands: ```export, env, ipconfig, ping, find, grep, split, cp, sort```

> My pocket-list of "less-used" CL commands: ```chmod, alias, xargs, git clone```

---


---

What does `ls` do? What do `ls -a`, `ls -l`, and `ls -lh` do? What combinations of those flags are meaningful?

> `ls` lists all files and subdirectories in a directory.

> `ls -a` lists all hidden files and subdirectories.

> `ls -l` lists files and subdirectories with long details.

> `ls -lh` lists files and subdirectories with long details and filesizes are displayed in human-readable sizes e.g. 10K, 10M, etc.

> `ls -lh` is quite meaningful since it provides a long details such as file access/restrictions.

---


---

What does `xargs` do? Give an example of how to use it.

> `xargs` takes arguments from standard input and executes it.

> I have not used xargs at all. So, I found a very useful tool to back up files using commandline.

> `find . -name '*~' -print 0 | xargs -0 -I % cp % ~/backups`


---
