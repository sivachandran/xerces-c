
configure_file(
    format: 'cmake@',
    input: 'Xerces_autoconf_config.hpp.cmake.in',
    output: 'Xerces_autoconf_config.hpp',
    configuration: config_data)

configure_file(
    input: 'XercesVersion.hpp.cmake.in',
    output: 'XercesVersion.hpp',
    configuration: config_data)

if host_system == 'windows'
    configure_file(
        input: 'version.rc.cmake.in',
        output: 'version.rc',
        configuration: config_data)
endif
