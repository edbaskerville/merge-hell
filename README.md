## squashy, rebasey, mergy

Start a new repo on GitHub with a readme, and clone it:

```sh
gh repo clone edbaskerville/{squashy | rebasey | mergy}
```

Start working on an issue branch:

```sh
git checkout -b issue1
```

Make a file `main.py` and put some lines into it:

```
x = 1
y = 2
```

Commit this change:

```sh
git add main.py
git commit -m "Initial parameter values"
```

and then add an extra line:

```
x = 1
y = 2
z = x + y
```

and commit this one and push:

```sh
git add main.py
git commit -m "Initial computation"
git push
```

At this point, request a PR on this change, and start working on a new issue related to the same bit of code.
Pretty confident this PR will be fine, so optimistically just base this branch on `issue1`.
Somebody can review the PR while the next one is worked on.
If conflicts arise because of PR review changes, so be it.
But if there are no changes, we shouldn't have to worry about it, right?

```sh
git checkout -b issue2
```

While working on `issue2`  notice that actually we want `x = 5` going forward, so `main.py` becomes:

```
x = 5
y = 2
z = x + y
```

We commit this change:

```
git add main.py
git commit -m "Change value of x"
```

and do another one:

```
x = 5
y = 2
z = x + y
print(z)
```

```
git add main.py
git commit -m "Implement output of computation"
```

and we push this branch:

```
git push
```

Now the first PR gets reviewed, and is successfully {squashed and merged | rebased and merged | merged}.

Then let's make a PR from `issue2`.

In the **squash merge case**, we get conflicts!!!

In the **rebase merge case**, we get conflicts!!!

In the **merge case**, we get no conflicts.
