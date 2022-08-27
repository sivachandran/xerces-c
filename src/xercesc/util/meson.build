
configure_file(
    format: 'cmake@',
    input: 'Xerces_autoconf_config.hpp.cmake.in',
    output: 'Xerces_autoconf_config.hpp',
    configuration: config_data)

configure_file(
    format: 'cmake@',
    input: 'XercesVersion.hpp.cmake.in',
    output: 'XercesVersion.hpp',
    configuration: config_data)

if host_system == 'windows'
    configure_file(
        format: 'cmake@',
        input: 'version.rc.cmake.in',
        output: 'version.rc',
        encoding: 'cp1252',
        configuration: config_data)
endif
