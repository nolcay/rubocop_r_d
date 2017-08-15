Git Hooks
=========

Git hooks are stored under `[repository]/.git/hooks`. The default ones have the
extention `.sample`. That means that they don't get executed. For them to get
executed, you just remove the `.sample` extention. At the top of the script you
have to provide a hashbang, i.e. `#!/usr/bin/env ruby`. After the hasbang, you
just write your code that you want to execute.

The hook scripts also need to have the `+x` permission. You can achieve this by
entering the command `chmod +x [your hook name here]`.

Filenames other than the existing ones (i.e. `pre-commit` and `post-commit`)
will not work. You have to put your code in the existing files.

Rubocop Pre Commit Hook
=======================

[I found this rubocop pre-commit hook](https://gist.github.com/mpeteuil/6147292)
that runs all staged or modified `.rb` files through rubocop. To utilize this
script, you just replace the existing code in the `pre-commit` hook with the
code in the gist file. There are a few errors in the gist, the fixed one can be
found in the hooks of this git repository. For it to work you (obviously) need
the `rubocop` gem.
