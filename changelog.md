# 0.6.4

+ Update dependencies
+ Minor cleanup

# 0.6.3

+ Update dependencies

# 0.6.2

+ License under the MPL-2.0
+ Publish to crates.io

# 0.6.1

+ Create supporting directories if they do not exist

# 0.6.0 sabanus

- Breaking change: `load` now requires the path to be part of the plugin definition

    zr load author/plugin some/file.zsh

Now must be

    zr load author/plugin/some/file.zsh

This fixes a lot of brittleness

# 0.5.0

+ Added sample zshrc benchmark
- Removed `add` and `reset`

# 0.4.8

+ Added output when cloning repositories
- Deprecated `add` and `reset`, as `load` is fast enough, and you can regen when mtime is different via

    [[ ~/.zshrc -nt ~/.zr/init.zsh ]] && { zr load \ ... }

# 0.4.6 fink

Added `load` command, which is about twice as fast as generating init.zsh.
If you had a *zshrc* that looked like:

    zr add some/plugin
    zr add other/plugin some/file.zsh

You can migrate to

    zr load \
      some/plugin \
      other/plugin some/file.zsh

Which will generate everything in one go.

This might be fast enough to always regenerate init.zsh on shell load.

Also added benchmarks, which can be run on nightly now.

# 0.4.3 neotoma

This is the first public release of zr!

Thank you to [SX91](https://github.com/SX91) for contributing fixes for linux.
