project('xerces-c', ['c','cpp'],
        version: '3.2.3',
        license: 'Apache v2.0',
        default_options: [
            'default_library=static',
        ])

source_root = meson.current_source_dir()
build_root = meson.current_build_dir()
host_system = host_machine.system()

cxx = meson.get_compiler('cpp')

# TODO: read versions from configure.ac file
xercesc_version = meson.project_version()
interface_version = '3.2'
grammar_serialization_level = '7'

xerces_version_parts = xercesc_version.split('.')
xercesc_version_major = xerces_version_parts[0].to_int()
xercesc_version_minor = xerces_version_parts[1].to_int()
xercesc_version_revision = xerces_version_parts[2].to_int()

interface_version_parts = interface_version.split('.')
interface_version_major = interface_version_parts[0].to_int()
interface_version_minor = interface_version_parts[1].to_int()

config_data = configuration_data()
config_data.set('VERSION', xercesc_version)
config_data.set('XERCES_VERSION_MAJOR', xercesc_version_major)
config_data.set('XERCES_VERSION_MINOR', xercesc_version_minor)
config_data.set('XERCES_VERSION_REVISION', xercesc_version_revision)
config_data.set('INTERFACE_VERSION_MAJOR', interface_version_major)
config_data.set('INTERFACE_VERSION_MINOR', interface_version_minor)
config_data.set('INTERFACE_VERSION_D', '@0@.@1@'.format(interface_version_major, interface_version_minor))
config_data.set('INTERFACE_VERSION_U', '@0@_@1@'.format(interface_version_major, interface_version_minor))
config_data.set('XERCES_GRAMMAR_SERIALIZATION_LEVEL', grammar_serialization_level)

### Begin Xerces Warnings ###
compiler_args = []
if cxx.get_id() == 'gcc' or cxx.get_id() == 'clang'
    compiler_args += [
      '-Wall',
      '-Wcast-align',
      '-Wcast-qual',
      '-Wctor-dtor-privacy',
      '-Wextra',
      '-Wformat=2',
      '-Wimplicit-atomic-properties',
      '-Wmissing-declarations',
      '-Wno-long-long',
      '-Woverlength-strings',
      '-Woverloaded-virtual',
      '-Wredundant-decls',
      '-Wreorder',
      '-Wswitch-default',
      '-Wunused-variable',
      '-Wwrite-strings',
      '-Wno-variadic-macros',
      '-fstrict-aliasing',
    ]

    if get_option('extra-warnings')
        compiler_args += [
            '-Wfloat-equal',
            '-Wmissing-prototypes',
            '-Wunreachable-code'
        ]
    endif

    if get_option('fatal-warnings')
        compiler_args += ['-Werror']
    endif
elif cxx.get_id() == 'msvc'
    if get_option('extra-warnings')
        compiler_args += ['/W4']
    endif

    if get_option('fatal-warnings')
        compiler_args += ['-WX']
    endif
endif

add_global_arguments(cxx.get_supported_arguments(compiler_args), language: ['c', 'cpp'])
### End Xerces Warnings

### Begin Xerces Includes ###
config_data.set('HAVE_ARPA_INET_H', 0)
if cxx.has_header('arpa/inet.h')
    config_data.set('HAVE_ARPA_INET_H', 1)
endif

config_data.set('HAVE_DLFCN_H', 0)
if cxx.has_header('dlfcn.h')
    config_data.set('HAVE_DLFCN_H', 1)
endif

config_data.set('HAVE_FCNTL_H', 0)
if cxx.has_header('fcntl.h')
    config_data.set('HAVE_FCNTL_H', 1)
endif

config_data.set('HAVE_FLOAT_H', 0)
if cxx.has_header('float.h')
    config_data.set('HAVE_FLOAT_H', 1)
endif

config_data.set('HAVE_LANGINFO_H', 0)
if cxx.has_header('langinfo.h')
    config_data.set('HAVE_LANGINFO_H', 1)
endif

config_data.set('HAVE_LIMITS_H', 0)
if cxx.has_header('limits.h')
    config_data.set('HAVE_LIMITS_H', 1)
endif

config_data.set('HAVE_LOCALE_H', 0)
if cxx.has_header('locale.h')
    config_data.set('HAVE_LOCALE_H', 1)
endif

config_data.set('HAVE_MEMORY_H', 0)
if cxx.has_header('memory.h')
    config_data.set('HAVE_MEMORY_H', 1)
endif

config_data.set('HAVE_NETDB_H', 0)
if cxx.has_header('netdb.h')
    config_data.set('HAVE_NETDB_H', 1)
endif

config_data.set('HAVE_NETINET_IN_H', 0)
if cxx.has_header('netinet/in.h')
    config_data.set('HAVE_NETINET_IN_H', 1)
endif

config_data.set('HAVE_NL_TYPES_H', 0)
if cxx.has_header('nl_types.h')
    config_data.set('HAVE_NL_TYPES_H', 1)
endif

config_data.set('HAVE_STDBOOL_H', 0)
if cxx.has_header('stdbool.h')
    config_data.set('HAVE_STDBOOL_H', 1)
endif

config_data.set('HAVE_STDDEF_H', 0)
if cxx.has_header('stddef.h')
    config_data.set('HAVE_STDDEF_H', 1)
endif

config_data.set('HAVE_STDLIB_H', 0)
if cxx.has_header('stdlib.h')
    config_data.set('HAVE_STDLIB_H', 1)
endif

config_data.set('HAVE_STRING_H', 0)
if cxx.has_header('string.h')
    config_data.set('HAVE_STRING_H', 1)
endif

config_data.set('HAVE_STRINGS_H', 0)
if cxx.has_header('strings.h')
    config_data.set('HAVE_STRINGS_H', 1)
endif

config_data.set('HAVE_SYS_PARAM_H', 0)
if cxx.has_header('sys/param.h')
    config_data.set('HAVE_SYS_PARAM_H', 1)
endif

config_data.set('HAVE_SYS_SOCKET_H', 0)
if cxx.has_header('sys/socket.h')
    config_data.set('HAVE_SYS_SOCKET_H', 1)
endif

config_data.set('HAVE_SYS_STAT_H', 0)
if cxx.has_header('sys/stat.h')
    config_data.set('HAVE_SYS_STAT_H', 1)
endif

config_data.set('HAVE_SYS_TIME_H', 0)
if cxx.has_header('sys/time.h')
    config_data.set('HAVE_SYS_TIME_H', 1)
endif

config_data.set('HAVE_SYS_TIMEB_H', 0)
if cxx.has_header('sys/timeb.h')
    config_data.set('HAVE_SYS_TIMEB_H', 1)
endif

config_data.set('HAVE_SYS_TYPES_H', 0)
if cxx.has_header('sys/types.h')
    config_data.set('HAVE_SYS_TYPES_H', 1)
endif

config_data.set('HAVE_UNISTD_H', 0)
if cxx.has_header('unistd.h')
    config_data.set('HAVE_UNISTD_H', 1)
endif

config_data.set('HAVE_WCHAR_H', 0)
if cxx.has_header('wchar.h')
    config_data.set('HAVE_WCHAR_H', 1)
endif

config_data.set('HAVE_WCTYPE_H', 0)
if cxx.has_header('wctype.h')
    config_data.set('HAVE_WCTYPE_H', 1)
endif

config_data.set('HAVE_ENDIAN_H', 0)
if cxx.has_header('endian.h')
    config_data.set('HAVE_ENDIAN_H', 1)
endif

config_data.set('HAVE_MACHINE_ENDIAN_H', 0)
if cxx.has_header('machine/endian.h')
    config_data.set('HAVE_MACHINE_ENDIAN_H', 1)
endif

config_data.set('HAVE_MACHINE_ENDIAN_H', 0)
if cxx.has_header('arpa/nameser_compat.h')
    config_data.set('HAVE_ARPA_NAMESER_COMPAT_H', 1)
endif

config_data.set('XERCES_HAVE_SYS_TYPES_H', config_data.get('HAVE_SYS_TYPES_H'))
### End Xerces Includes

### Begin Xerces Functions ###
config_data.get('HAVE_GETCWD', 0)
if cxx.has_function('getcwd')
    config_data.set('HAVE_GETCWD', 1)
endif

config_data.get('HAVE_PATHCONF', 0)
if cxx.has_function('pathconf')
    config_data.set('HAVE_PATHCONF', 1)
endif

config_data.get('HAVE_REALPATH', 0)
if cxx.has_function('realpath')
    config_data.set('HAVE_REALPATH', 1)
endif

config_data.get('HAVE_GETADDRINFO', 0)
if cxx.has_function('getaddrinfo')
    config_data.set('HAVE_GETADDRINFO', 1)
endif

config_data.get('HAVE_GETHOSTBYADDR', 0)
if cxx.has_function('gethostbyaddr')
    config_data.set('HAVE_GETHOSTBYADDR', 1)
endif

config_data.get('HAVE_GETHOSTBYNAME', 0)
if cxx.has_function('gethostbyname')
    config_data.set('HAVE_GETHOSTBYNAME', 1)
endif

config_data.get('HAVE_SOCKET', 0)
if cxx.has_function('socket')
    config_data.set('HAVE_SOCKET', 1)
endif

config_data.get('HAVE_CLOCK_GETTIME', 0)
if cxx.has_function('clock_gettime')
    config_data.set('HAVE_CLOCK_GETTIME', 1)
endif

config_data.get('HAVE_FTIME', 0)
if cxx.has_function('ftime')
    config_data.set('HAVE_FTIME', 1)
endif

config_data.get('HAVE_GETTIMEOFDAY', 0)
if cxx.has_function('gettimeofday')
    config_data.set('HAVE_GETTIMEOFDAY', 1)
endif

config_data.get('HAVE_GMTIME_R', 0)
if cxx.has_function('gmtime_r')
    config_data.set('HAVE_GMTIME_R', 1)
endif

config_data.get('HAVE_MEMMOVE', 0)
if cxx.has_function('memmove')
    config_data.set('HAVE_MEMMOVE', 1)
endif

config_data.get('HAVE_MEMSET', 0)
if cxx.has_function('memset')
    config_data.set('HAVE_MEMSET', 1)
endif

config_data.get('HAVE_NL_LANGINFO', 0)
if cxx.has_function('nl_langinfo')
    config_data.set('HAVE_NL_LANGINFO', 1)
endif

config_data.get('HAVE_SETLOCALE', 0)
if cxx.has_function('setlocale')
    config_data.set('HAVE_SETLOCALE', 1)
endif

config_data.get('HAVE_LOCALECONV', 0)
if cxx.has_function('localeconv')
    config_data.set('HAVE_LOCALECONV', 1)
endif

config_data.get('HAVE_SNPRINTF', 0)
if cxx.has_function('snprintf')
    config_data.set('HAVE_SNPRINTF', 1)
endif

config_data.get('HAVE_STRCASECMP', 0)
if cxx.has_function('strcasecmp')
    config_data.set('HAVE_STRCASECMP', 1)
endif

config_data.get('HAVE_STRNCASECMP', 0)
if cxx.has_function('strncasecmp')
    config_data.set('HAVE_STRNCASECMP', 1)
endif

config_data.get('HAVE_STRICMP', 0)
if cxx.has_function('stricmp')
    config_data.set('HAVE_STRICMP', 1)
endif

config_data.get('HAVE_STRNICMP', 0)
if cxx.has_function('strnicmp')
    config_data.set('HAVE_STRNICMP', 1)
endif

config_data.get('HAVE_STRCHR', 0)
if cxx.has_function('strchr')
    config_data.set('HAVE_STRCHR', 1)
endif

config_data.get('HAVE_STRDUP', 0)
if cxx.has_function('strdup')
    config_data.set('HAVE_STRDUP', 1)
endif

config_data.get('HAVE_STRRCHR', 0)
if cxx.has_function('strrchr')
    config_data.set('HAVE_STRRCHR', 1)
endif

config_data.get('HAVE_STRSTR', 0)
if cxx.has_function('strstr')
    config_data.set('HAVE_STRSTR', 1)
endif

config_data.get('HAVE_STRTOL', 0)
if cxx.has_function('strtol')
    config_data.set('HAVE_STRTOL', 1)
endif

config_data.get('HAVE_STRTOUL', 0)
if cxx.has_function('strtoul')
    config_data.set('HAVE_STRTOUL', 1)
endif

config_data.get('HAVE_TIMEGM', 0)
if cxx.has_function('timegm')
    config_data.set('HAVE_TIMEGM', 1)
endif

config_data.get('HAVE_TOWUPPER', 0)
if cxx.has_function('towupper')
    config_data.set('HAVE_TOWUPPER', 1)
endif

config_data.get('HAVE_TOWLOWER', 0)
if cxx.has_function('towlower')
    config_data.set('HAVE_TOWLOWER', 1)
endif

config_data.get('HAVE_MBLEN', 0)
if cxx.has_function('mblen')
    config_data.set('HAVE_MBLEN', 1)
endif

config_data.get('HAVE_WCSUPR', 0)
if cxx.has_function('wcsupr')
    config_data.set('HAVE_WCSUPR', 1)
endif

config_data.get('HAVE_WCSLWR', 0)
if cxx.has_function('wcslwr')
    config_data.set('HAVE_WCSLWR', 1)
endif

config_data.get('HAVE_WCSNICMP', 0)
if cxx.has_function('wcsnicmp')
    config_data.set('HAVE_WCSNICMP', 1)
endif

config_data.get('HAVE_WCSICMP', 0)
if cxx.has_function('wcsicmp')
    config_data.set('HAVE_WCSICMP', 1)
endif
### End Xerces Functions ###

### Begin Xerces DLL ###
config_data.set('XERCES_PLATFORM_EXPORT', '')
config_data.set('XERCES_PLATFORM_IMPORT', '')
config_data.set('XERCES_TEMPLATE_EXTERN', 'extern')
config_data.set('XERCES_DLL_EXPORT', 0)
config_data.set('XERCES_STATIC_LIBRARY', 0)

if get_option('default_library') == 'static'
    config_data.set('XERCES_STATIC_LIBRARY', 1)
else
    if host_system == 'windows'
        config_data.set('XERCES_PLATFORM_EXPORT', '__declspec(dllexport)')
        config_data.set('XERCES_PLATFORM_IMPORT', '__declspec(dllimport)')
        if cxx.get_id() == 'msvc'
            config_data.set('XERCES_TEMPLATE_EXTERN', '')
        endif
        config_data.set('XERCES_DLL_EXPORT', 1)
    endif
endif
### End Xerces DLL ###

### Begin NetAccessor Selection ###
libsocket = cxx.find_library('socket', required: false)
libnsl = cxx.find_library('nsl', required: false)

netaccessors = []

if host_system == 'windows'
    if cxx.has_header('winsock2.h')
        config_data.set('HAVE_WINSOCK2_H', 1)
        netaccessors += 'winsock'
    endif
else
    libcurl = cxx.find_library('curl', required: false)
    netaccessors += 'curl'

    if cxx.has_header('sys/socket.h')
        config_data.set('HAVE_SYS_SOCKET_H', 1)
        netaccessors += 'socket'
    endif

    if cxx.has_header('CoreServices/CoreServices.h')
        core_services_library = cxx.find_library('CoreServices')
        if core_services_library.found()
            netaccessors += 'cfurl'
        endif
    endif
endif

if netaccessors.length() == 0
    error('no netaccessor available')
endif

config_data.set('XERCES_USE_NETACCESSOR_CURL', 0)
config_data.set('XERCES_USE_NETACCESSOR_SOCKET', 0)
config_data.set('XERCES_USE_NETACCESSOR_CFURL', 0)
config_data.set('XERCES_USE_NETACCESSOR_WINSOCK', 0)
if netaccessors[0] == 'curl'
    config_data.set('XERCES_USE_NETACCESSOR_CURL', 1)
elif netaccessors[0] == 'socket'
    config_data.set('XERCES_USE_NETACCESSOR_SOCKET', 1)
elif netaccessors[0] == 'cfurl'
    config_data.set('XERCES_USE_NETACCESSOR_CFURL', 1)
elif netaccessors[0] == 'winsock'
    config_data.set('XERCES_USE_NETACCESSOR_WINSOCK', 1)
else
    error('invalid netaccessor' + netaccessors[0])
endif
### End NetAccessor Selection ###

### Begin Transcoder Selection ###
transcoders = []

icu = cxx.find_library('icu', required: false)
if icu.found()
    transcoders += 'icu'
endif

if host_system == 'darwin'
    if cxx.has_header('CoreServices/CoreServices.h')
        core_services_library = cxx.find_library('CoreServices')
        if core_services_library.found()
            transcoders += 'macosunicodeconverter'
        endif
    endif
endif

if cxx.has_header('iconv.h')
    config_data.set('HAVE_ICONV_H', 1)
endif

if cxx.has_header('wchar.h')
    config_data.set('HAVE_WCHAR_H', 1)
endif

if cxx.has_header('string.h')
    config_data.set('HAVE_STRING_H', 1)
endif

if cxx.has_header('stdlib.h')
    config_data.set('HAVE_STDLIB_H', 1)
endif

if cxx.has_header('stdio.h')
    config_data.set('HAVE_STDIO_H', 1)
endif

if cxx.has_header('ctype.h')
    config_data.set('HAVE_CTYPE_H', 1)
endif

if cxx.has_header('locale.h')
    config_data.set('HAVE_LOCALE_H', 1)
endif

if cxx.has_header('errno.h')
    config_data.set('HAVE_ERRNO_H', 1)
endif

if cxx.has_header('endian.h')
    config_data.set('HAVE_ENDIAN_H', 1)
endif

if cxx.has_header('machine/endian.h')
    config_data.set('HAVE_MACHINE_ENDIAN_H', 1)
endif

if cxx.has_header('arpa/nameser_compat.h')
    config_data.set('HAVE_ARPA_NAMESER_COMPAT_H', 1)
endif

if cxx.has_header('arpa/nameser_compat.h')
    config_data.set('HAVE_ARPA_NAMESER_COMPAT_H', 1)
endif

if cxx.has_function('iconv_open')
    config_data.set('HAVE_ICONV_OPEN', 1)
endif

if cxx.has_function('iconv_close')
    config_data.set('HAVE_ICONV_CLOSE', 1)
endif

if cxx.has_function('iconv')
    config_data.set('HAVE_ICONV', 1)
endif

if config_data.get('HAVE_ICONV_H') == 1 and \
    config_data.get('HAVE_WCHAR_H') == 1 and \
    config_data.get('HAVE_STRING_H') == 1 and \
    config_data.get('HAVE_STDLIB_H') == 1 and \
    config_data.get('HAVE_STDIO_H') == 1 and \
    config_data.get('HAVE_CTYPE_H') == 1 and \
    config_data.get('HAVE_LOCALE_H') == 1 and \
    config_data.get('HAVE_ERRNO_H') == 1
    if config_data.get('HAVE_ENDIAN_H') == 1 or \
        config_data.get('HAVE_MACHINE_ENDIAN_H') == 1 or \
        config_data.get('HAVE_ARPA_NAMESER_COMPAT_H') == 1
        if config_data.get('HAVE_ICONV_OPEN') == 1 and \
            config_data.get('HAVE_ICONV_CLOSE') == 1 and \
            config_data.get('HAVE_ICONV') == 1
            transcoders += 'gnuiconv'
        endif
    endif
endif

if host_system == 'windows'
    transcoders += 'windows'
endif

if cxx.has_function('mblen')
    config_data.set('HAVE_MBLEN', 1)
endif

if cxx.has_function('wcstombs')
    config_data.set('HAVE_WCSTOMBS', 1)
endif

if cxx.has_function('mbstowcs')
    config_data.set('HAVE_MBSTOWCS', 1)
endif

if config_data.get('HAVE_WCHAR_H') == 1 and \
    config_data.get('HAVE_MBLEN') == 1 and \
    config_data.get('HAVE_WCSTOMBS') == 1 and \
    config_data.get('HAVE_MBSTOWCS') == 1
    transcoders += 'iconv'
endif

if transcoders.length() == 0
    error('no transcoders found')
endif

config_data.set('XERCES_USE_TRANSCODER_ICU', 0)
config_data.set('XERCES_USE_TRANSCODER_ICONV', 0)
config_data.set('XERCES_USE_TRANSCODER_GNUICONV', 0)
config_data.set('XERCES_USE_TRANSCODER_MACOSUNICODECONVERTER', 0)
config_data.set('XERCES_USE_TRANSCODER_WINDOWS', 0)

if transcoders[0] == 'icu'
    config_data.set('XERCES_USE_TRANSCODER_ICU', 1)
elif transcoders[0] == 'iconv'
    config_data.set('XERCES_USE_TRANSCODER_ICONV', 1)
elif transcoders[0] == 'gnuiconv'
    config_data.set('XERCES_USE_TRANSCODER_GNUICONV', 1)
elif transcoders[0] == 'macosunicodeconverter'
    config_data.set('XERCES_USE_TRANSCODER_MACOSUNICODECONVERTER', 1)
elif transcoders[0] == 'windows'
    config_data.set('XERCES_USE_TRANSCODER_WINDOWS', 1)
else
    error('invalid transcoder ' + transcoders[0])
endif
### End Transcoder Selection ###

### Begin MsgLoaders ###
msgloaders = []

icu = cxx.find_library('icu', required: false)
if icu.found()
    msgloaders += 'icu'
endif

if cxx.has_header('nl_types.h')
    config_data.set('HAVE_NLTYPES_H', 1)
endif

if cxx.has_function('catopen')
    config_data.set('HAVE_CATOPEN', 1)
endif

if cxx.has_function('catclose')
    config_data.set('HAVE_CATCLOSE', 1)
endif

if cxx.has_function('catgets')
    config_data.set('HAVE_CATGETS', 1)
endif

if config_data.get('HAVE_NLTYPES_H') == 1 and \
    config_data.get('HAVE_CATOPEN') == 1 and \
    config_data.get('HAVE_CATCLOSE') == 1 and \
    config_data.get('HAVE_CATGETS') == 1
    msgloaders += 'iconv'
endif

if msgloaders.length() == 0
    error('no msgloaders found')
endif

config_data.set('XERCES_USE_MSGLOADER_ICU', 0)
config_data.set('XERCES_USE_MSGLOADER_ICONV', 0)
config_data.set('XERCES_USE_MSGLOADER_INMEMORY', 0)

if msgloaders[0] == 'icu'
    config_data.set('XERCES_USE_MSGLOADER_ICU', 1)
elif msgloaders[0] == 'iconv'
    config_data.set('XERCES_USE_MSGLOADER_ICONV', 1)
elif msgloaders[0] == 'inmemory'
    config_data.set('XERCES_USE_MSGLOADER_INMEMORY', 1)
else
    error('invalid message loader ' + msgloaders[0])
endif
### End MsgLoaders ###

### Begin MutexMgr Selection ###
mutexmgrs = []

threads = true
if not get_option('threads')
    threads = false
endif

if threads
    threads_prefer_pthread = true
    add_global_arguments('-D_THREAD_SAFE=1', language: 'cpp')

    code = '''
#include <thread>
#include <mutex>
#include <iostream>

namespace
{

  std::mutex m1;
  std::recursive_mutex m2;

  void
  threadmain()
  {
    std::lock_guard<std::mutex> lock1(m1);
    std::lock_guard<std::recursive_mutex> lock2(m2);
    std::cout << \"In thread\" << std::endl;
  }

}

int main() {
  std::thread foo(threadmain);
  foo.join();

  return 0;
}
'''
    if cxx.compiles(code, name: 'std::thread check')
        mutexmgrs += 'standard'
    endif

    threads_dep = dependency('threads')
    if threads_dep.found()
        if host_system == 'windows'
            mutexmgrs += 'windows'
        else
            mutexmgrs += 'posix'
            config_data.set('HAVE_PTHREAD', 1)
        endif
    endif
endif

mutexmgrs += 'nothreads'

if mutexmgrs.length() == 0
    error('no mutexmgr found')
endif

config_data.set('XERCES_USE_MUTEXMGR_STD', 0)
config_data.set('XERCES_USE_MUTEXMGR_POSIX', 0)
config_data.set('XERCES_USE_MUTEXMGR_WINDOWS', 0)
config_data.set('XERCES_USE_MUTEXMGR_NOTHREAD', 0)
if mutexmgrs[0] == 'standard'
    config_data.set('XERCES_USE_MUTEXMGR_STD', 1)
elif mutexmgrs[0] == 'posix'
    config_data.set('XERCES_USE_MUTEXMGR_POSIX', 1)
elif mutexmgrs[0] == 'windows'
    config_data.set('XERCES_USE_MUTEXMGR_WINDOWS', 1)
elif mutexmgrs[0] == 'nothreads'
    config_data.set('XERCES_USE_MUTEXMGR_NOTHREAD', 1)
else
    error('invalid mutex manager ' + mutexmgrs[0])
endif
### End MutexMgr Selection ###

### Begin FileMgr Selection ###
config_data.set('XERCES_USE_FILEMGR_POSIX', 0)
config_data.set('XERCES_USE_FILEMGR_WINDOWS', 0)

filemgr = ''
if host_system == 'windows'
    config_data.set('XERCES_USE_FILEMGR_WINDOWS', 1)
    filemgr = 'windows'
elif host_system == 'linux'
    config_data.set('XERCES_USE_FILEMGR_POSIX', 1)
    filemgr = 'POSIX'
else
    error('invalid file manager ' + host_system)
endif
### End FileMgr Selection ###

configure_file(
    format: 'cmake@',
    input: 'config.h.cmake.in',
    output: 'config.h',
    configuration: config_data)

subdir('src')
subdir('src/xercesc/util')

summary = [
    '',
    'Xerces-C++ configuration summary',
    '--------------------------------',
    '',
    '  Version:                   ' + xercesc_version,
    '  Library interface version: ' + interface_version,
    '',
    '  Installation directory:    ' + get_option('prefix'),
    '  C compiler:                ' + meson.get_compiler('c').cmd_array()[0],
    '  C++ compiler:              ' + meson.get_compiler('cpp').cmd_array()[0],
    '',
    '  Build shared libraries:    ' + (get_option('default_library') == 'shared').to_string(),
    ##message('  Path delimiters:           \"${path_delims}\"',
    '  File Manager:              ' + filemgr,
    '  Mutex Manager:             ' + mutexmgrs[0],
    '  Transcoder:                ' + transcoders[0],
    '  NetAccessor:               ' + netaccessors[0],
    '  Message Loader:            ' + msgloaders[0],
]
message('\n'.join(summary))

# TODO: message('  XMLCh type:                ' + ${xmlch_type}')
