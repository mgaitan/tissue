Tisú
====

Your project's issue tracker, in a text file

Note: this is a work in progress. Pull requests and feedback are welcome.

Install
-------

$ [sudo] pip3 install -U tisu

Usage
-----

Tisú can import and export your issues using a simple markdown file, where each section
is a different issue.

```
# issue title

issue body

```

If an issue already exists in your tracker, the number is a sufix in the title.

```
# issue title [#1]
```

In this case, Tisú will update that issue instead to create a new one.

This is the current command line help::

```
(tissue)tin@morochita:~$ tisu --help
Tisú: your issue tracker, in a text file

Usage:
  tisu push <markdown_file> <repo> [--user=<user>] [--pass=<pass>]
  tisu pull <markdown_file> <repo> [--state=<state>]

Options:
  -h --help         Show this screen.
  --version         Show version.
  --state=<state>   Filter by issue state [default: open].
  --user=<user>     Github username to send issues. Repo's username if no given.
  --pass=<pass>     Github password. Prompt if no given.
```

Example
-------

Suppose you want to push a couple of issues like in
[this TODO.md](https://github.com/mgaitan/tisu/blob/caf8cdd34d7dea04e7e36a23a4e08748364f09c5/TODO.md)
file.

```
$ tisu push TODO.md mgaitan/tisu
Github password:
Created #11: support metadata
Created #12: setup travis CI
```

Result in:

![](https://cloud.githubusercontent.com/assets/2355719/13778398/451fa440-ea94-11e5-985d-84d8770cf531.png)

Then, I can pull and overwrite the file.

```
$ tisu pull TODO.md mgaitan/tisu
```

[This is the result](https://github.com/mgaitan/tisu/blob/07c478a15f0dd12b5f5ba1a7636f9703e9f201fc/TODO.md).
As in this case I didn't change anything online, the content is (almost) the same, but note that
each title has its ID number.


