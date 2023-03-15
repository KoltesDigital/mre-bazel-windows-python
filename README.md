# MRE: Bazel + Windows + Python platform

This repo is a minimal reproducible example of a bug with Bazel on Windows when a specific Python platform is used.

Run:

```
bazel run //:requirements.update --platforms=//:some_platform
```

Current output:

```
INFO: Running command line: bazel-bin/requirements.update.exe ./requirements.in ./requirements.txt None None None //:requirements.update
LAUNCHER ERROR: Cannot launch process: "C:/users/XYZ/_bazel_XYZ/random/execroot/__main__/bazel-out/x64_windows-fastbuild/bin/external/bazel_tools/tools/python/py3wrapper.sh" C:\Users\XYZ\_bazel_XYZ\random\execroot\__main__\bazel-out\x64_windows-fastbuild\bin\requirements.update.zip ./requirements.in ./requirements.txt None None None //:requirements.update
Reason: (error: 193): %1 is not a valid Win32 application.
```
