# Stripping ed

## REGEX testing

- Find and replace all instances: `,s/line/replaced/g`
- Find and replace all instances where `line` is the first expression: `,s/^line/replaced/g`

This project is meant to strip the grep regex engine out of ed.
Since all we need is a text processor, the approach is sort of straight forward.....
Firstly, we need to identify what is the heart of the grep component.

These functions stand out the most:

- compile
- execute
- backref
- cclass


Now, we need to figure out how on Earth they work and tinker with a regular expression engine works.

## compile

Defined macros and their meanings:

- CCIRC: "^" symbol is ingested and this regex symbol denotes the beginning of a line. We want to peek forward to see the value after the carat. For example, "^Hello" will match "Hello World" but not "World, Hello" and the value of peek char would be "H".
- CEOF: signals that we are at the end of the file. We only need this for reading from STDIN.




# External Links

- [ED Regular Expression Syntax Documentation](https://www.gnu.org/software/gnulib/manual/html_node/ed-regular-expression-syntax.html)
- [GNU 'ed' Manual](https://www.gnu.org/software/ed/manual/ed_manual.html)
- [Using 'ed' YouTube video](https://www.youtube.com/watch?v=UQOHNT36ioQ)
- [Computer Hope Article on 'ed'](https://www.computerhope.com/unix/ued.htm)
- [Linux Die Manual Page](https://linux.die.net/man/1/ed)

# Using git

- [How can I restore a previous version of my project](https://www.git-tower.com/learn/git/faq/restore-repo-to-previous-revision)
- [Git commit history](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)
