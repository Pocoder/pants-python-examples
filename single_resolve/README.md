```shell
pants dependencies single_resolve/third/main.py
```

give the following warning:

```
[WARN] The target single_resolve/third/main.py imports `numpy`, but Pants cannot safely infer a dependency because more than one target owns this module, so it is ambiguous which to use: ['single_resolve/first:first', 'single_resolve/second:second'].

Please explicitly include the dependency you want in the `dependencies` field of single_resolve/third/main.py, or ignore the ones you do not want by prefixing with `!` or `!!` so that one or no targets are left.

Alternatively, you can remove the ambiguity by deleting/changing some of the targets so that only 1 target owns this module. Refer to https://www.pantsbuild.org/2.29/docs/using-pants/troubleshooting-common-issues#import-errors-and-missing-dependencies.
[WARN] Pants cannot infer owners for the following imports in the target single_resolve/third/main.py:

  * numpy (line: 1)

If you do not expect an import to be inferable, add `# pants: no-infer-dep` to the import line. Otherwise, see https://www.pantsbuild.org/2.29/docs/using-pants/troubleshooting-common-issues#import-errors-and-missing-dependencies for common problems.
```
