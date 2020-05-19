cc_library(
  name = "freealut",
  hdrs = glob([
      "include/*.h",
      "src/*.h",
      ]),
  srcs = [
      'src/alutBufferData.c',
      'src/alutCodec.c',
      'src/alutError.c',
      'src/alutInit.c',
      'src/alutInputStream.c',
      'src/alutLoader.c',
      'src/alutOutputStream.c',
      'src/alutUtil.c',
      'src/alutVersion.c',
      'src/alutWaveform.c',
      ],
  includes = [
      'src',
      'include',
  ],
  deps = select({
      "//platforms:win32": [
          '//3rdparty/mccarthy-bindeps/alsoft',
      ],
      "//conditions:default": [ 
         # TODO: Link against OpenAL
      ],
  }),
  linkopts = select({
      "//platforms:win32": [
      ],
      "//conditions:default": [
          '-lopenal',
      ],
  }),
  defines = select({
      "//platforms:win32": [
          '_WIN32',
          'HAVE___INT8',
          'HAVE_WINDOWS_H',
          'HAVE_SLEEP',
          'ALUT_BUILD_LIBRARY',
          'HAVE__STAT',
      ],
      "//conditions:default": [
          'HAVE_STDINT_H',
          'HAVE_USLEEP',
          'HAVE_UNISTD_H',
          'HAVE_STAT',
      ],
      }),
  visibility = ["//visibility:public"],
  )
