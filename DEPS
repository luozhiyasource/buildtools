use_relative_paths = True

vars = {
  'chromium_url': 'https://chromium.googlesource.com',

  # TODO(crbug.com/1177288): Remove this file. Please don't add to it.

  # TODO(crbug.com/941824): The values below need to be kept in sync
  # between //DEPS and //buildtools/DEPS, so if you're updating one,
  # update the other. There is a presubmit check that checks that
  # you've done so; if you are adding new tools to //buildtools and
  # hence new revisions to this list, make sure you update the
  # _CheckBuildtoolsRevsAreInSync in PRESUBMIT.py to include the additional
  # revisions.

  # GN CIPD package version.
  'gn_version': 'git_revision:dfcbc6fed0a8352696f92d67ccad54048ad182b3',

  # When changing these, also update the svn revisions in deps_revisions.gni
  # TODO(crbug.com/1166332) rename to clang_format_revision.
  'clang_fmt_revision':    '99803d74e35962f63a775f29477882afd4d57d94',
  'libcxx_revision':       '8fa87946779682841e21e2da977eccfb6cb3bded',
}

deps = {
  'clang_format/script':
    Var('chromium_url') +
    '/external/github.com/llvm/llvm-project/clang/tools/clang-format.git@' +
    Var('clang_fmt_revision'),
  'linux64': {
    'packages': [
      {
        'package': 'gn/gn/linux-amd64',
        'version': Var('gn_version'),
      }
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "linux"',
  },
  'mac': {
    'packages': [
      {
        'package': 'gn/gn/mac-amd64',
        'version': Var('gn_version'),
      }
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "mac"',
  },
  'third_party/libc++/trunk':
    Var('chromium_url') +
    '/external/github.com/llvm/llvm-project/libcxx.git' + '@' +
    Var('libcxx_revision'),
  'win': {
    'packages': [
      {
        'package': 'gn/gn/windows-amd64',
        'version': Var('gn_version'),
      }
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "win"',
  },
}
