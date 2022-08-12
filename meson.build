project('xerces-c', 'cpp',
        version: '3.2.3',
        license: 'Apache v2.0',
        default_options: 'default_library=static')

source_root = meson.current_source_dir()
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


configure_file(
    format: 'cmake@',
    input: 'config.h.cmake.in',
    output: 'config.h',
    configuration: config_data)

subdir('src')
subdir('src/xercesc/util')
