# IntelliJ Plugin Sync Issue

When this repo is opened by IntelliJ with the Bazel plugin, the sync fails with messages:

```
python_info.bzl:47:8: name 'PyInfo' is not defined (did you mean 'CcInfo'?)
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

python_info.bzl:89:43: name 'PyInfo' is not defined (did you mean 'CcInfo'?)
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

python_info.bzl:96:19: name 'PyInfo' is not defined (did you mean 'CcInfo'?)
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:57:24: name 'JavaInfo' is not defined (did you mean 'java_info'?)
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:87:30: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:91:8: name 'JavaPluginInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:92:27: name 'JavaPluginInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:101:30: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:106:39: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:109:27: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:112:39: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:118:30: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:126:23: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:140:20: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:149:40: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:177:12: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:199:70: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)

java_info.bzl:230:25: name 'JavaInfo' is not defined
Analyzing: target //.bazelbsp/config:module_container (6 packages loaded, 0 targets configured)
```

Uncommenting this [line](https://github.com/styurin/intellij-demo/blob/main/.bazelrc#L1) allows
the plugin to sync:

```
#common --noincompatible_disable_autoloads_in_main_repo
```

Note that not providing this option is equivalent to this (note no `no` before `incompatible`):

```
common --incompatible_disable_autoloads_in_main_repo
```
