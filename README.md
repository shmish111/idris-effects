# Idris Effects

This is the same library as that which is included in Idris but in a separate repository. This makes it neater to build projects using Bazel with [rules_idris](https://github.com/BryghtWords/rules_idris).

## Use

To use effects in a bazel project, add the following to your `WORKSPACE` file:

```python
git_repository(
    name = "idris-effects",
    remote = "https://github.com/shmish111/idris-effects.git",
    commit = "89068f067085e8f342a8a7c8809a543fcffd3f5e",
)
```

Then in a `BUILD` file you can depend on effects, e.g.

```python
idris_library (
    name = "mylib",
    deps = ["@idris-effects//:effects"],
    srcs = native.glob(["**/*.idr"]),
    visibility = ["//visibility:public"],
)
```
