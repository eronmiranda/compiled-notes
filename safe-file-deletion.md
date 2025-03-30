# How to Avoid Accidentally Deleting the Wrong Files in Linux

Ever tried to delete files with a pattern like `*.txt`, but ended up wiping out the wrong ones because of a tiny typo? It happens. Here's an example of this common mistake:

## The Problem

Imagine you meant to delete all `.txt` files, but you accidentally added a space after the `*`:

```sh
$ ls
somefile another-file  a.txt   b.txt   c.txt  confidential  very-important-file  passwords
$ rm * .txt  # DANGER!! Don't run this! Deletes the wrong files!
```

🚨 Oops! 🚨

That space caused `rm` to delete everything in that directory before `.txt`, not just the `.txt` files

## A Safer Method: Verify Before Deleting

This simple two-steps approach helps you avoid accidental deletions:

### Step 1: Check Before You Delete

Instead of jumping straight to `rm`, first `ls` the files you plan to delete:

```sh
$ ls *.txt
a.txt   b.txt   c.txt
```

If that looks right, you’re good to proceed. If not, you just saved yourself from a mistake!

### 2. Delete using `rm !$`

Once you’ve verified the correct files, delete them safely:

```sh
$ rm !$
rm *.txt
```

#### How It Works

`!$` (read: “bang dollar”) takes the last argument from your previous command.
So, rm !$ is the same as typing:

```sh
rm *.txt
```

No need to retype the pattern—just use ls first, and you can be sure you’re deleting the right files.

#### Catching Mistakes Before They Happen

If you accidentally insert a space, `ls` will warn you safely:

```sh
$ ls * .txt
/bin/ls: cannot access '.txt': No such file or directory
somefile another-file  a.txt   b.txt   c.txt  confidential  very-important-file  passwords
```

Since `ls` doesn’t delete files, you can catch the error early and fix it before running `rm`.

## Final Thoughts

By simply running `ls` before `rm !$` you:

- see what you're about to delete
- prevent accidental file losss
- save time and avoid headaches 🤕
