Demo for https://github.com/bazelbuild/bazel/issues/13904

run `bazel cquery 'deps(//:foo)'`: I get nothing. If I change .bazelversion back to 4.1.0, I get correct output.
more info:

* my OS: macOS Big Sur: version 11.5.2 (20G95)
* my python versions:

```
➜  bazel-13094 git:(main) python --version
Python 2.7.16
➜  bazel-13094 git:(main) python3 --version
Python 3.7.9
```

* my xcode info:

```
➜  bazel-13094 git:(main) xcrun --version     
xcrun version 59.
➜  bazel-13094 git:(main) xcode-select -v
xcode-select version 2384.
➜  bazel-13094 git:(main) clang -v
Apple clang version 12.0.0 (clang-1200.0.32.29)
Target: x86_64-apple-darwin20.6.0
Thread model: posix
InstalledDir: /Library/Developer/CommandLineTools/usr/bin
```

# 4.2.0

Output of `bazel info release`:

```
4.2.0
```

Output of `bazel cquery 'deps(//:foo)' 2>& | pcopy`: (macOS magic to copy stderr and stdout to pasteboard (clipboard))

```
INFO: Invocation ID: 41f8f4e7-d667-45ba-8454-68198a8cb18d
Loading: 
Loading: 0 packages loaded
Analyzing: 0 targets (0 packages loaded, 0 targets configured)
INFO: Analyzed 0 targets (0 packages loaded, 0 targets configured).
INFO: Found 0 targets...
INFO: Empty query results
INFO: Elapsed time: 0.170s
INFO: 0 processes.
INFO: Build completed successfully, 0 total actions
INFO: Build completed successfully, 0 total actions
```

# 4.1.0

Output of `bazel info release`:

```
4.1.0
```

Output of `bazel cquery 'deps(//:foo)' 2>& | pcopy`: (macOS magic to copy stderr and stdout to pasteboard (clipboard))

```
INFO: Invocation ID: 6d042eac-6aea-4fbf-80a3-5f1a109ea8a4
Loading: 
Loading: 0 packages loaded
Analyzing: target //:foo (0 packages loaded, 0 targets configured)
INFO: Analyzed target //:foo (0 packages loaded, 0 targets configured).
INFO: Found 1 target...
//:foo (c5956fc)
@bazel_tools//tools/cpp:toolchain (c5956fc)
@local_config_cc//:cc-compiler-darwin (HOST)
@bazel_tools//tools/zip:zipper (HOST)
@bazel_tools//tools/launcher:launcher (HOST)
@bazel_tools//tools/python:toolchain_type (c5956fc)
@bazel_tools//tools/cpp:grep-includes (HOST)
@bazel_tools//tools/python:2to3 (HOST)
@pip_pypi__requests//:pkg (c5956fc)
//:foo.py (null)
@local_config_platform//:host (c5956fc)
@bazel_tools//tools/python:_autodetecting_py_runtime_pair (HOST)
@bazel_tools//tools/cpp:toolchain_type (c5956fc)
@pip_pypi__requests//:requests/utils.py (null)
@pip_pypi__requests//:requests/packages.py (null)
@pip_pypi__urllib3//:pkg (c5956fc)
@pip_pypi__requests//:requests-2.26.0.dist-info/METADATA (null)
@pip_pypi__requests//:requests-2.26.0.dist-info/WHEEL (null)
@pip_pypi__requests//:requests/_internal_utils.py (null)
@local_config_cc//:local (HOST)
@pip_pypi__requests//:requests/hooks.py (null)
@local_config_cc//:compiler_deps (HOST)
@bazel_tools//tools/build_defs/cc/whitelists/starlark_hdrs_check:loose_header_check_allowed_in_toolchain (null)
@pip_pypi__requests//:requests/help.py (null)
@pip_pypi__requests//:requests/status_codes.py (null)
@pip_pypi__requests//:requests-2.26.0.dist-info/LICENSE (null)
@pip_pypi__requests//:requests/exceptions.py (null)
@pip_pypi__requests//:requests/sessions.py (null)
@pip_pypi__requests//:requests/cookies.py (null)
@local_config_platform//:host (HOST)
@pip_pypi__requests//:requests-2.26.0.dist-info/top_level.txt (null)
@pip_pypi__requests//:requests/compat.py (null)
@pip_pypi__idna//:pkg (c5956fc)
@bazel_tools//tools/cpp:link_dynamic_library (HOST)
@platforms//cpu:x86_64 (c5956fc)
@pip_pypi__requests//:requests/api.py (null)
@pip_pypi__requests//:requests/certs.py (null)
@bazel_tools//src/conditions:windows (HOST)
@pip_pypi__requests//:requests/adapters.py (null)
@pip_pypi__requests//:requests/__version__.py (null)
@pip_pypi__charset_normalizer//:pkg (c5956fc)
@bazel_tools//tools/cpp:interface_library_builder (HOST)
@bazel_tools//tools/python:_autodetecting_py3_runtime (HOST)
@bazel_tools//src/tools/launcher:launcher (HOST)
@bazel_tools//tools/zip:zipper/zipper (null)
@pip_pypi__requests//:requests/structures.py (null)
@bazel_tools//tools/build_defs/cc/whitelists/parse_headers_and_layering_check:disabling_parse_headers_and_layering_check_allowed (null)
@local_config_cc//:module.modulemap (null)
@platforms//os:osx (c5956fc)
@pip_pypi__requests//:requests/models.py (null)
@bazel_tools//src/conditions:remote (HOST)
@bazel_tools//tools/cpp:grep-includes.sh (null)
@local_config_cc//:empty (HOST)
@local_config_cc//:toolchain (c5956fc)
@bazel_tools//src/conditions:host_windows (HOST)
@pip_pypi__requests//:requests/__init__.py (null)
@pip_pypi__certifi//:pkg (c5956fc)
@bazel_tools//tools/python:_autodetecting_py2_runtime (HOST)
@pip_pypi__requests//:requests-2.26.0.dist-info/RECORD (null)
@pip_pypi__requests//:requests/auth.py (null)
@local_config_cc//:cc_wrapper (HOST)
@pip_pypi__urllib3//:urllib3/packages/backports/__init__.py (null)
@pip_pypi__charset_normalizer//:charset_normalizer/legacy.py (null)
@pip_pypi__urllib3//:urllib3/util/connection.py (null)
@pip_pypi__urllib3//:urllib3-1.26.6.dist-info/top_level.txt (null)
@pip_pypi__idna//:idna/codec.py (null)
@pip_pypi__certifi//:certifi/__main__.py (null)
@platforms//cpu:x86_64 (HOST)
@pip_pypi__urllib3//:urllib3/util/timeout.py (null)
@bazel_tools//tools/cpp:link_dynamic_library.sh (null)
@bazel_tools//tools/cpp:malloc (HOST)
@pip_pypi__urllib3//:urllib3/contrib/pyopenssl.py (null)
@pip_pypi__urllib3//:urllib3/util/response.py (null)
@local_config_cc//:cc-compiler-darwin (c5956fc)
@pip_pypi__urllib3//:urllib3-1.26.6.dist-info/LICENSE.txt (null)
@pip_pypi__idna//:idna-3.2.dist-info/WHEEL (null)
@pip_pypi__charset_normalizer//:charset_normalizer-2.0.4.dist-info/top_level.txt (null)
@pip_pypi__urllib3//:urllib3/packages/ssl_match_hostname/_implementation.py (null)
@platforms//os:windows (HOST)
@bazel_tools//tools/cpp:build_interface_so (null)
@pip_pypi__certifi//:certifi-2021.5.30.dist-info/METADATA (null)
@pip_pypi__charset_normalizer//:charset_normalizer-2.0.4.dist-info/WHEEL (null)
@pip_pypi__charset_normalizer//:charset_normalizer/md.py (null)
@pip_pypi__idna//:idna/idnadata.py (null)
@pip_pypi__urllib3//:urllib3/contrib/securetransport.py (null)
@pip_pypi__urllib3//:urllib3/contrib/_securetransport/bindings.py (null)
@pip_pypi__idna//:idna/compat.py (null)
@pip_pypi__urllib3//:urllib3/packages/__init__.py (null)
@pip_pypi__urllib3//:urllib3/contrib/_appengine_environ.py (null)
@pip_pypi__urllib3//:urllib3/_collections.py (null)
@pip_pypi__charset_normalizer//:charset_normalizer/cli/normalizer.py (null)
@pip_pypi__certifi//:certifi-2021.5.30.dist-info/LICENSE (null)
@pip_pypi__urllib3//:urllib3/util/queue.py (null)
@pip_pypi__urllib3//:urllib3/poolmanager.py (null)
@pip_pypi__urllib3//:urllib3/packages/six.py (null)
@pip_pypi__urllib3//:urllib3/fields.py (null)
@pip_pypi__urllib3//:urllib3/contrib/_securetransport/low_level.py (null)
@pip_pypi__idna//:idna/core.py (null)
@pip_pypi__charset_normalizer//:charset_normalizer/cli/__init__.py (null)
@pip_pypi__charset_normalizer//:charset_normalizer/api.py (null)
@pip_pypi__charset_normalizer//:charset_normalizer/version.py (null)
@bazel_tools//tools/cpp:toolchain_type (HOST)
@pip_pypi__urllib3//:urllib3-1.26.6.dist-info/WHEEL (null)
@pip_pypi__charset_normalizer//:charset_normalizer-2.0.4.dist-info/entry_points.txt (null)
@pip_pypi__charset_normalizer//:charset_normalizer-2.0.4.dist-info/METADATA (null)
@pip_pypi__certifi//:certifi/core.py (null)
@pip_pypi__urllib3//:urllib3/util/ssltransport.py (null)
@bazel_tools//src/tools/launcher:dummy.cc (null)
@pip_pypi__idna//:idna/intranges.py (null)
@pip_pypi__urllib3//:urllib3/packages/ssl_match_hostname/__init__.py (null)
@pip_pypi__urllib3//:urllib3/contrib/appengine.py (null)
@pip_pypi__idna//:idna-3.2.dist-info/LICENSE.md (null)
@pip_pypi__urllib3//:urllib3/contrib/__init__.py (null)
@pip_pypi__charset_normalizer//:charset_normalizer/py.typed (null)
@pip_pypi__charset_normalizer//:charset_normalizer/__init__.py (null)
@pip_pypi__charset_normalizer//:charset_normalizer/assets/__init__.py (null)
@pip_pypi__certifi//:certifi-2021.5.30.dist-info/RECORD (null)
@pip_pypi__charset_normalizer//:charset_normalizer/cd.py (null)
@pip_pypi__urllib3//:urllib3/contrib/socks.py (null)
@pip_pypi__urllib3//:urllib3/util/url.py (null)
@pip_pypi__certifi//:certifi/cacert.pem (null)
@pip_pypi__charset_normalizer//:charset_normalizer-2.0.4.dist-info/LICENSE (null)
@pip_pypi__urllib3//:urllib3/util/wait.py (null)
@platforms//os:os (c5956fc)
@local_config_cc//:builtin_include_directory_paths (null)
@pip_pypi__urllib3//:urllib3/_version.py (null)
@bazel_tools//tools/cpp:toolchain (HOST)
@pip_pypi__urllib3//:urllib3/filepost.py (null)
@pip_pypi__urllib3//:urllib3/response.py (null)
@pip_pypi__charset_normalizer//:charset_normalizer/constant.py (null)
@pip_pypi__urllib3//:urllib3/util/proxy.py (null)
@pip_pypi__charset_normalizer//:charset_normalizer/models.py (null)
@pip_pypi__urllib3//:urllib3/request.py (null)
@bazel_tools//tools/def_parser:def_parser (HOST)
@pip_pypi__urllib3//:urllib3/connectionpool.py (null)
@pip_pypi__charset_normalizer//:charset_normalizer/utils.py (null)
@pip_pypi__certifi//:certifi/__init__.py (null)
@platforms//cpu:cpu (c5956fc)
@pip_pypi__urllib3//:urllib3/__init__.py (null)
@pip_pypi__urllib3//:urllib3/util/retry.py (null)
@platforms//os:osx (HOST)
@bazel_tools//tools/python:py2wrapper.sh (HOST)
@pip_pypi__certifi//:certifi-2021.5.30.dist-info/top_level.txt (null)
@pip_pypi__urllib3//:urllib3-1.26.6.dist-info/METADATA (null)
@bazel_tools//tools/python:py3wrapper.sh (HOST)
@pip_pypi__idna//:idna/uts46data.py (null)
@pip_pypi__certifi//:certifi-2021.5.30.dist-info/WHEEL (null)
@pip_pypi__urllib3//:urllib3/connection.py (null)
@pip_pypi__urllib3//:urllib3-1.26.6.dist-info/RECORD (null)
@pip_pypi__idna//:idna/package_data.py (null)
@pip_pypi__urllib3//:urllib3/contrib/_securetransport/__init__.py (null)
@pip_pypi__urllib3//:urllib3/util/ssl_.py (null)
@pip_pypi__idna//:idna/py.typed (null)
@pip_pypi__charset_normalizer//:charset_normalizer-2.0.4.dist-info/RECORD (null)
@pip_pypi__urllib3//:urllib3/util/request.py (null)
@pip_pypi__idna//:idna/__init__.py (null)
@pip_pypi__idna//:idna-3.2.dist-info/RECORD (null)
@pip_pypi__urllib3//:urllib3/contrib/ntlmpool.py (null)
@pip_pypi__urllib3//:urllib3/exceptions.py (null)
@local_config_cc//:cc-compiler-armeabi-v7a (c5956fc)
@pip_pypi__urllib3//:urllib3/util/__init__.py (null)
@pip_pypi__urllib3//:urllib3/packages/backports/makefile.py (null)
@pip_pypi__idna//:idna-3.2.dist-info/METADATA (null)
@pip_pypi__idna//:idna-3.2.dist-info/top_level.txt (null)
@bazel_tools//tools/cpp:link_dynamic_library (62353eb)
@bazel_tools//tools/def_parser:no_op.bat (null)
@bazel_tools//tools/cpp:interface_library_builder (62353eb)
@local_config_cc//:compiler_deps (62353eb)
@local_config_cc//:stub_armeabi-v7a (c5956fc)
@local_config_cc//:local (c5956fc)
@platforms//cpu:cpu (HOST)
@platforms//os:os (HOST)
@bazel_tools//tools/python:_generate_wrappers (HOST)
@local_config_cc//:empty (62353eb)
@local_config_cc//:toolchain (HOST)
@local_config_cc//:cc_wrapper.sh (null)
@local_config_cc//:cc-compiler-armeabi-v7a (HOST)
@local_config_platform//:host (62353eb)
@local_config_cc//:cc_wrapper (62353eb)
@bazel_tools//tools/python:pywrapper_template.txt (null)
@platforms//os:osx (62353eb)
@local_config_cc//:stub_armeabi-v7a (HOST)
@platforms//cpu:x86_64 (62353eb)
@platforms//os:os (62353eb)
@platforms//cpu:cpu (62353eb)
INFO: Elapsed time: 0.198s
INFO: 0 processes.
INFO: Build completed successfully, 0 total actions
INFO: Build completed successfully, 0 total actions
```
