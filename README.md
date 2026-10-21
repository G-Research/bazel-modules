# bazel-modules

A collection of [Bazel](https://bazel.build) modules developed and maintained by [G-Research](https://github.com/G-Research).

## Repository layout

Each module lives in its own top-level directory with its own `MODULE.bazel`:

```
bazel-modules/
├── <module_name>/
│   ├── MODULE.bazel
│   ├── BUILD.bazel
│   └── README.md
└── README.md
```

Each module's `README.md` covers its own purpose, usage, and supported Bazel versions.

## Using a module

These modules use [Bzlmod](https://bazel.build/external/module). Add the module to your `MODULE.bazel`:

```starlark
bazel_dep(name = "<module_name>", version = "<version>")
```

If a module isn't published to a registry yet, you can pull it straight from this repository:

```starlark
bazel_dep(name = "<module_name>")

git_override(
    module_name = "<module_name>",
    remote = "https://github.com/G-Research/bazel-modules.git",
    commit = "<commit_sha>",
    strip_prefix = "<module_name>",
)
```

## Contributing

Contributions are welcome. Please open an issue to discuss significant changes before submitting a pull request.

When adding a new module:

1. Create a new top-level directory named after the module.
2. Add a `MODULE.bazel` with the module's name and version.
3. Include a `README.md` describing what the module provides and how to use it.

## License

See [LICENSE](LICENSE) for details.
