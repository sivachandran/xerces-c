
source_root = meson.current_source_dir()

dom_sources = [
    'xercesc/dom/DOMException.cpp',
    'xercesc/dom/DOMLSException.cpp',
    'xercesc/dom/DOMRangeException.cpp',
    'xercesc/dom/DOMXPathException.cpp',
]

domimpl_sources = [
    'xercesc/dom/impl/DOMAttrImpl.cpp',
    'xercesc/dom/impl/DOMAttrMapImpl.cpp',
    'xercesc/dom/impl/DOMAttrNSImpl.cpp',
    'xercesc/dom/impl/DOMCDATASectionImpl.cpp',
    'xercesc/dom/impl/DOMCharacterDataImpl.cpp',
    'xercesc/dom/impl/DOMChildNode.cpp',
    'xercesc/dom/impl/DOMCommentImpl.cpp',
    'xercesc/dom/impl/DOMConfigurationImpl.cpp',
    'xercesc/dom/impl/DOMDeepNodeListImpl.cpp',
    'xercesc/dom/impl/DOMDocumentFragmentImpl.cpp',
    'xercesc/dom/impl/DOMDocumentImpl.cpp',
    'xercesc/dom/impl/DOMDocumentTypeImpl.cpp',
    'xercesc/dom/impl/DOMElementImpl.cpp',
    'xercesc/dom/impl/DOMElementNSImpl.cpp',
    'xercesc/dom/impl/DOMEntityImpl.cpp',
    'xercesc/dom/impl/DOMEntityReferenceImpl.cpp',
    'xercesc/dom/impl/DOMErrorImpl.cpp',
    'xercesc/dom/impl/DOMImplementationImpl.cpp',
    'xercesc/dom/impl/DOMImplementationListImpl.cpp',
    'xercesc/dom/impl/DOMImplementationRegistry.cpp',
    'xercesc/dom/impl/DOMLocatorImpl.cpp',
    'xercesc/dom/impl/DOMNamedNodeMapImpl.cpp',
    'xercesc/dom/impl/DOMNodeIDMap.cpp',
    'xercesc/dom/impl/DOMNodeImpl.cpp',
    'xercesc/dom/impl/DOMNodeIteratorImpl.cpp',
    'xercesc/dom/impl/DOMNodeListImpl.cpp',
    'xercesc/dom/impl/DOMNodeVector.cpp',
    'xercesc/dom/impl/DOMNormalizer.cpp',
    'xercesc/dom/impl/DOMNotationImpl.cpp',
    'xercesc/dom/impl/DOMParentNode.cpp',
    'xercesc/dom/impl/DOMProcessingInstructionImpl.cpp',
    'xercesc/dom/impl/DOMRangeImpl.cpp',
    'xercesc/dom/impl/DOMStringListImpl.cpp',
    'xercesc/dom/impl/DOMStringPool.cpp',
    'xercesc/dom/impl/DOMTextImpl.cpp',
    'xercesc/dom/impl/DOMTreeWalkerImpl.cpp',
    'xercesc/dom/impl/DOMTypeInfoImpl.cpp',
    'xercesc/dom/impl/DOMLSSerializerImpl.cpp',
    'xercesc/dom/impl/DOMLSInputImpl.cpp',
    'xercesc/dom/impl/DOMLSOutputImpl.cpp',
    'xercesc/dom/impl/DOMXPathExpressionImpl.cpp',
    'xercesc/dom/impl/DOMXPathNSResolverImpl.cpp',
    'xercesc/dom/impl/DOMXPathResultImpl.cpp',
    'xercesc/dom/impl/XSDElementNSImpl.cpp',
]

framework_sources = [
    'xercesc/framework/BinOutputStream.cpp',
    'xercesc/framework/LocalFileFormatTarget.cpp',
    'xercesc/framework/LocalFileInputSource.cpp',
    'xercesc/framework/MemBufFormatTarget.cpp',
    'xercesc/framework/MemBufInputSource.cpp',
    'xercesc/framework/psvi/PSVIAttribute.cpp',
    'xercesc/framework/psvi/PSVIAttributeList.cpp',
    'xercesc/framework/psvi/PSVIElement.cpp',
    'xercesc/framework/psvi/PSVIItem.cpp',
    'xercesc/framework/psvi/XSAnnotation.cpp',
    'xercesc/framework/psvi/XSAttributeDeclaration.cpp',
    'xercesc/framework/psvi/XSAttributeGroupDefinition.cpp',
    'xercesc/framework/psvi/XSAttributeUse.cpp',
    'xercesc/framework/psvi/XSComplexTypeDefinition.cpp',
    'xercesc/framework/psvi/XSElementDeclaration.cpp',
    'xercesc/framework/psvi/XSFacet.cpp',
    'xercesc/framework/psvi/XSIDCDefinition.cpp',
    'xercesc/framework/psvi/XSModel.cpp',
    'xercesc/framework/psvi/XSModelGroup.cpp',
    'xercesc/framework/psvi/XSModelGroupDefinition.cpp',
    'xercesc/framework/psvi/XSMultiValueFacet.cpp',
    'xercesc/framework/psvi/XSNamespaceItem.cpp',
    'xercesc/framework/psvi/XSNotationDeclaration.cpp',
    'xercesc/framework/psvi/XSObject.cpp',
    'xercesc/framework/psvi/XSParticle.cpp',
    'xercesc/framework/psvi/XSSimpleTypeDefinition.cpp',
    'xercesc/framework/psvi/XSTypeDefinition.cpp',
    'xercesc/framework/psvi/XSValue.cpp',
    'xercesc/framework/psvi/XSWildcard.cpp',
    'xercesc/framework/StdInInputSource.cpp',
    'xercesc/framework/StdOutFormatTarget.cpp',
    'xercesc/framework/URLInputSource.cpp',
    'xercesc/framework/Wrapper4DOMLSInput.cpp',
    'xercesc/framework/Wrapper4InputSource.cpp',
    'xercesc/framework/XMLAttDef.cpp',
    'xercesc/framework/XMLAttDefList.cpp',
    'xercesc/framework/XMLAttr.cpp',
    'xercesc/framework/XMLBuffer.cpp',
    'xercesc/framework/XMLBufferMgr.cpp',
    'xercesc/framework/XMLContentModel.cpp',
    'xercesc/framework/XMLDTDDescription.cpp',
    'xercesc/framework/XMLElementDecl.cpp',
    'xercesc/framework/XMLEntityDecl.cpp',
    'xercesc/framework/XMLFormatter.cpp',
    'xercesc/framework/XMLGrammarDescription.cpp',
    'xercesc/framework/XMLGrammarPoolImpl.cpp',
    'xercesc/framework/XMLNotationDecl.cpp',
    'xercesc/framework/XMLRecognizer.cpp',
    'xercesc/framework/XMLRefInfo.cpp',
    'xercesc/framework/XMLSchemaDescription.cpp',
    'xercesc/framework/XMLValidator.cpp',
]

internal_sources = [
    'xercesc/internal/BinFileOutputStream.cpp',
    'xercesc/internal/BinMemOutputStream.cpp',
    'xercesc/internal/DGXMLScanner.cpp',
    'xercesc/internal/ElemStack.cpp',
    'xercesc/internal/IGXMLScanner.cpp',
    'xercesc/internal/IGXMLScanner2.cpp',
    'xercesc/internal/MemoryManagerImpl.cpp',
    'xercesc/internal/ReaderMgr.cpp',
    'xercesc/internal/SGXMLScanner.cpp',
    'xercesc/internal/ValidationContextImpl.cpp',
    'xercesc/internal/VecAttributesImpl.cpp',
    'xercesc/internal/VecAttrListImpl.cpp',
    'xercesc/internal/WFXMLScanner.cpp',
    'xercesc/internal/XMLReader.cpp',
    'xercesc/internal/XMLScanner.cpp',
    'xercesc/internal/XMLScannerResolver.cpp',
    'xercesc/internal/XProtoType.cpp',
    'xercesc/internal/XSAXMLScanner.cpp',
    'xercesc/internal/XSerializeEngine.cpp',
    'xercesc/internal/XSObjectFactory.cpp',
    'xercesc/internal/XTemplateSerializer.cpp',
]

parsers_sources = [
    'xercesc/parsers/AbstractDOMParser.cpp',
    'xercesc/parsers/DOMLSParserImpl.cpp',
    'xercesc/parsers/SAX2XMLFilterImpl.cpp',
    'xercesc/parsers/SAX2XMLReaderImpl.cpp',
    'xercesc/parsers/SAXParser.cpp',
    'xercesc/parsers/XercesDOMParser.cpp',
]

sax_sources = [
    'xercesc/sax/Dummy.cpp',
    'xercesc/sax/InputSource.cpp',
    'xercesc/sax/SAXException.cpp',
    'xercesc/sax/SAXParseException.cpp',
]

sax2_sources = [
    'xercesc/sax2/sax2Dummy.cpp',
]

util_sources = [
    'xercesc/util/Base64.cpp',
    'xercesc/util/BinFileInputStream.cpp',
    'xercesc/util/BinInputStream.cpp',
    'xercesc/util/BinMemInputStream.cpp',
    'xercesc/util/BitSet.cpp',
    'xercesc/util/DefaultPanicHandler.cpp',
    'xercesc/util/EncodingValidator.cpp',
    'xercesc/util/HeaderDummy.cpp',
    'xercesc/util/HexBin.cpp',
    'xercesc/util/JanitorExports.cpp',
    'xercesc/util/KVStringPair.cpp',
    'xercesc/util/Mutexes.cpp',
    'xercesc/util/PanicHandler.cpp',
    'xercesc/util/PlatformUtils.cpp',
    'xercesc/util/PSVIUni.cpp',
    'xercesc/util/QName.cpp',
    'xercesc/util/regx/ASCIIRangeFactory.cpp',
    'xercesc/util/regx/BlockRangeFactory.cpp',
    'xercesc/util/regx/BMPattern.cpp',
    'xercesc/util/regx/CharToken.cpp',
    'xercesc/util/regx/ClosureToken.cpp',
    'xercesc/util/regx/ConcatToken.cpp',
    'xercesc/util/regx/Match.cpp',
    'xercesc/util/regx/Op.cpp',
    'xercesc/util/regx/OpFactory.cpp',
    'xercesc/util/regx/ParenToken.cpp',
    'xercesc/util/regx/ParserForXMLSchema.cpp',
    'xercesc/util/regx/RangeFactory.cpp',
    'xercesc/util/regx/RangeToken.cpp',
    'xercesc/util/regx/RangeTokenMap.cpp',
    'xercesc/util/regx/RegularExpression.cpp',
    'xercesc/util/regx/RegxParser.cpp',
    'xercesc/util/regx/RegxUtil.cpp',
    'xercesc/util/regx/StringToken.cpp',
    'xercesc/util/regx/Token.cpp',
    'xercesc/util/regx/TokenFactory.cpp',
    'xercesc/util/regx/UnicodeRangeFactory.cpp',
    'xercesc/util/regx/UnionToken.cpp',
    'xercesc/util/regx/XMLRangeFactory.cpp',
    'xercesc/util/regx/XMLUniCharacter.cpp',
    'xercesc/util/StringPool.cpp',
    'xercesc/util/SynchronizedStringPool.cpp',
    'xercesc/util/TransService.cpp',
    'xercesc/util/XMemory.cpp',
    'xercesc/util/XML256TableTranscoder.cpp',
    'xercesc/util/XML88591Transcoder.cpp',
    'xercesc/util/XMLAbstractDoubleFloat.cpp',
    'xercesc/util/XMLASCIITranscoder.cpp',
    'xercesc/util/XMLBigDecimal.cpp',
    'xercesc/util/XMLBigInteger.cpp',
    'xercesc/util/XMLChar.cpp',
    'xercesc/util/XMLChTranscoder.cpp',
    'xercesc/util/XMLDateTime.cpp',
    'xercesc/util/XMLDouble.cpp',
    'xercesc/util/XMLEBCDICTranscoder.cpp',
    'xercesc/util/XMLException.cpp',
    'xercesc/util/XMLFloat.cpp',
    'xercesc/util/XMLIBM1047Transcoder.cpp',
    'xercesc/util/XMLIBM1140Transcoder.cpp',
    'xercesc/util/XMLInitializer.cpp',
    'xercesc/util/XMLMsgLoader.cpp',
    'xercesc/util/XMLNumber.cpp',
    'xercesc/util/XMLString.cpp',
    'xercesc/util/XMLStringTokenizer.cpp',
    'xercesc/util/XMLUCS4Transcoder.cpp',
    'xercesc/util/XMLUni.cpp',
    'xercesc/util/XMLUri.cpp',
    'xercesc/util/XMLURL.cpp',
    'xercesc/util/XMLUTF16Transcoder.cpp',
    'xercesc/util/XMLUTF8Transcoder.cpp',
    'xercesc/util/XMLWin1252Transcoder.cpp',
]

validators_sources = [
    'xercesc/validators/common/AllContentModel.cpp',
    'xercesc/validators/common/CMAny.cpp',
    'xercesc/validators/common/CMBinaryOp.cpp',
    'xercesc/validators/common/CMUnaryOp.cpp',
    'xercesc/validators/common/ContentLeafNameTypeVector.cpp',
    'xercesc/validators/common/ContentSpecNode.cpp',
    'xercesc/validators/common/DFAContentModel.cpp',
    'xercesc/validators/common/Grammar.cpp',
    'xercesc/validators/common/GrammarResolver.cpp',
    'xercesc/validators/common/MixedContentModel.cpp',
    'xercesc/validators/common/SimpleContentModel.cpp',
    'xercesc/validators/datatype/AbstractNumericFacetValidator.cpp',
    'xercesc/validators/datatype/AbstractNumericValidator.cpp',
    'xercesc/validators/datatype/AbstractStringValidator.cpp',
    'xercesc/validators/datatype/AnySimpleTypeDatatypeValidator.cpp',
    'xercesc/validators/datatype/AnyURIDatatypeValidator.cpp',
    'xercesc/validators/datatype/Base64BinaryDatatypeValidator.cpp',
    'xercesc/validators/datatype/BooleanDatatypeValidator.cpp',
    'xercesc/validators/datatype/DatatypeValidator.cpp',
    'xercesc/validators/datatype/DatatypeValidatorFactory.cpp',
    'xercesc/validators/datatype/DateDatatypeValidator.cpp',
    'xercesc/validators/datatype/DateTimeDatatypeValidator.cpp',
    'xercesc/validators/datatype/DateTimeValidator.cpp',
    'xercesc/validators/datatype/DayDatatypeValidator.cpp',
    'xercesc/validators/datatype/DecimalDatatypeValidator.cpp',
    'xercesc/validators/datatype/DoubleDatatypeValidator.cpp',
    'xercesc/validators/datatype/DurationDatatypeValidator.cpp',
    'xercesc/validators/datatype/ENTITYDatatypeValidator.cpp',
    'xercesc/validators/datatype/FloatDatatypeValidator.cpp',
    'xercesc/validators/datatype/HexBinaryDatatypeValidator.cpp',
    'xercesc/validators/datatype/IDDatatypeValidator.cpp',
    'xercesc/validators/datatype/IDREFDatatypeValidator.cpp',
    'xercesc/validators/datatype/ListDatatypeValidator.cpp',
    'xercesc/validators/datatype/MonthDatatypeValidator.cpp',
    'xercesc/validators/datatype/MonthDayDatatypeValidator.cpp',
    'xercesc/validators/datatype/NameDatatypeValidator.cpp',
    'xercesc/validators/datatype/NCNameDatatypeValidator.cpp',
    'xercesc/validators/datatype/NOTATIONDatatypeValidator.cpp',
    'xercesc/validators/datatype/QNameDatatypeValidator.cpp',
    'xercesc/validators/datatype/StringDatatypeValidator.cpp',
    'xercesc/validators/datatype/TimeDatatypeValidator.cpp',
    'xercesc/validators/datatype/UnionDatatypeValidator.cpp',
    'xercesc/validators/datatype/XMLCanRepGroup.cpp',
    'xercesc/validators/datatype/YearDatatypeValidator.cpp',
    'xercesc/validators/datatype/YearMonthDatatypeValidator.cpp',
    'xercesc/validators/DTD/DTDAttDef.cpp',
    'xercesc/validators/DTD/DTDAttDefList.cpp',
    'xercesc/validators/DTD/DTDElementDecl.cpp',
    'xercesc/validators/DTD/DTDEntityDecl.cpp',
    'xercesc/validators/DTD/DTDGrammar.cpp',
    'xercesc/validators/DTD/DTDScanner.cpp',
    'xercesc/validators/DTD/DTDValidator.cpp',
    'xercesc/validators/DTD/XMLDTDDescriptionImpl.cpp',
    'xercesc/validators/schema/ComplexTypeInfo.cpp',
    'xercesc/validators/schema/GeneralAttributeCheck.cpp',
    'xercesc/validators/schema/identity/FieldActivator.cpp',
    'xercesc/validators/schema/identity/FieldValueMap.cpp',
    'xercesc/validators/schema/identity/IC_Field.cpp',
    'xercesc/validators/schema/identity/IC_Key.cpp',
    'xercesc/validators/schema/identity/IC_KeyRef.cpp',
    'xercesc/validators/schema/identity/IC_Selector.cpp',
    'xercesc/validators/schema/identity/IC_Unique.cpp',
    'xercesc/validators/schema/identity/IdentityConstraint.cpp',
    'xercesc/validators/schema/identity/IdentityConstraintHandler.cpp',
    'xercesc/validators/schema/identity/ValueStore.cpp',
    'xercesc/validators/schema/identity/ValueStoreCache.cpp',
    'xercesc/validators/schema/identity/XercesXPath.cpp',
    'xercesc/validators/schema/identity/XPathMatcher.cpp',
    'xercesc/validators/schema/identity/XPathMatcherStack.cpp',
    'xercesc/validators/schema/identity/XPathSymbols.cpp',
    'xercesc/validators/schema/NamespaceScope.cpp',
    'xercesc/validators/schema/SchemaAttDef.cpp',
    'xercesc/validators/schema/SchemaAttDefList.cpp',
    'xercesc/validators/schema/SchemaElementDecl.cpp',
    'xercesc/validators/schema/SchemaGrammar.cpp',
    'xercesc/validators/schema/SchemaInfo.cpp',
    'xercesc/validators/schema/SchemaSymbols.cpp',
    'xercesc/validators/schema/SchemaValidator.cpp',
    'xercesc/validators/schema/SubstitutionGroupComparator.cpp',
    'xercesc/validators/schema/TraverseSchema.cpp',
    'xercesc/validators/schema/XercesAttGroupInfo.cpp',
    'xercesc/validators/schema/XercesElementWildcard.cpp',
    'xercesc/validators/schema/XercesGroupInfo.cpp',
    'xercesc/validators/schema/XMLSchemaDescriptionImpl.cpp',
    'xercesc/validators/schema/XSDDOMParser.cpp',
    'xercesc/validators/schema/XSDErrorReporter.cpp',
    'xercesc/validators/schema/XSDLocator.cpp',
    'xercesc/validators/schema/XUtil.cpp',
]

xinclude_sources = [
    'xercesc/xinclude/XIncludeDOMDocumentProcessor.cpp',
    'xercesc/xinclude/XIncludeLocation.cpp',
    'xercesc/xinclude/XIncludeUtils.cpp',
]

icu_sources = [
    'xercesc/util/Transcoders/ICU/ICUTransService.cpp',
]

gnuiconv_sources = [
    'xercesc/util/Transcoders/IconvGNU/IconvGNUTransService.cpp',
]

iconv_sources = [
    'xercesc/util/Transcoders/Iconv/IconvTransService.cpp',
]

macosunicodeconverter_sources = [
    'xercesc/util/Transcoders/MacOSUnicodeConverter/MacOSUnicodeConverter.cpp',
]

wintrans_sources = [
    'xercesc/util/Transcoders/Win32/Win32TransService.cpp',
]

curl_sources = [
    'xercesc/util/NetAccessors/Curl/CurlNetAccessor.cpp',
    'xercesc/util/NetAccessors/Curl/CurlURLInputStream.cpp',
]

sockets_sources = [
    'xercesc/util/NetAccessors/Socket/SocketNetAccessor.cpp',
    'xercesc/util/NetAccessors/Socket/UnixHTTPURLInputStream.cpp',
    'xercesc/util/NetAccessors/BinHTTPInputStreamCommon.cpp',
]

cfurl_sources = [
    'xercesc/util/NetAccessors/MacOSURLAccessCF/MacOSURLAccessCF.cpp',
    'xercesc/util/NetAccessors/MacOSURLAccessCF/URLAccessCFBinInputStream.cpp',
]

winsock_sources = [
    'xercesc/util/NetAccessors/WinSock/WinSockNetAccessor.cpp',
    'xercesc/util/NetAccessors/WinSock/BinHTTPURLInputStream.cpp',
    'xercesc/util/NetAccessors/BinHTTPInputStreamCommon.cpp',
]

msginmemory_sources = [
    'xercesc/util/MsgLoaders/InMemory/InMemMsgLoader.cpp',
]

msgicu_sources = [
    'xercesc/util/MsgLoaders/ICU/ICUMsgLoader.cpp',
]

msgicu_nodist_sources = [
  source_root + '/xercesc_messages.c',
  source_root+ '/root_res.c',
]

msgiconv_sources = [
    'xercesc/util/MsgLoaders/MsgCatalog/MsgCatalogLoader.cpp',
]

posixfmgr_sources = [
    'xercesc/util/FileManagers/PosixFileMgr.cpp',
]

winfmgr_sources = [
    'xercesc/util/FileManagers/WindowsFileMgr.cpp',
]

nothreadmmgr_sources = [
    'xercesc/util/MutexManagers/NoThreadMutexMgr.cpp',
]

stdmmgr_sources = [
    'xercesc/util/MutexManagers/StdMutexMgr.cpp',
]

posixmmgr_sources = [
    'xercesc/util/MutexManagers/PosixMutexMgr.cpp',
]

winmmgr_sources = [
    'xercesc/util/MutexManagers/WindowsMutexMgr.cpp',
]

libxerces_c_sources = [
    util_sources,
    dom_sources,
    domimpl_sources,
    framework_sources,
    internal_sources,
    parsers_sources,
    sax_sources,
    sax2_sources,
    validators_sources,
    xinclude_sources,
]

libxerces_c_deps = []
libxerces_c_resources = []

# Add replacement functions
xerces_replacement_funcs = []
if not have_stricmp
    xerces_replacement_funcs += 'stricmp.c'
endif
if not have_strnicmp
    xerces_replacement_funcs += 'strnicmp.c'
endif
if not have_towlower
    xerces_replacement_funcs += 'towlower.c'
endif
if not have_towupper
    xerces_replacement_funcs += 'towupper.c'
endif
libxerces_c_sources += xerces_replacement_funcs

# NetAccessors, conditionally built based on selection
if libsocket.found()
    libxerces_c_deps += libsocket
endif

if libnsl.found()
    libxerces_c_deps += libnsl
endif

if netaccessors[0] == 'curl'
    libxerces_c_sources += curl_sources
    libxerces_c_deps += curl_dep
endif

if netaccessors[0] == 'socket'
    libxerces_c_sources += sockets_sources
endif

if netaccessors[0] == 'cfurl'
    libxerces_c_sources += cfurl_sources
    libxerces_c_deps += core_services_library
endif

if netaccessors[0] == 'winsock'
    libxerces_c_sources += winsock_sources
endif

# Transcoders, conditionally built based on selection
if transcoders[0] == 'icu'
    libxerces_c_sources += icu_sources
    libxerces_c_deps += libicu_dep
endif

if transcoders[0] == 'gnuiconv'
    libxerces_c_sources += gnuiconv_sources
endif

if transcoders[0] == 'iconv'
    libxerces_c_sources += iconv_sources
endif

if transcoders[0] == 'macosunicodeconverter'
    libxerces_c_sources += macosunicodeconverter_sources
    libxerces_c_deps += core_services_library
endif

if transcoders[0] == 'windows'
    libxerces_c_sources += wintrans_sources
endif

# MsgLoaders, conditionally built based on selection
if msgloaders[0] == 'inmemory'
    libxerces_c_sources += msginmemory_sources
endif

if msgloaders[0] == 'icu'
    libxerces_c_sources += msgicu_sources
    libxerces_c_sources += msgicu_nodist_sources
    libxerces_c_deps += libicu_dep

    pkgname = 'xercesc_messages_' + config_data.get('INTERFACE_VERSION_U')

    custom_target(
        'xercesc_messages.c',
        output: ['xercesc_messages.c'],
        input: [source_root + 'xercesc/util/MsgLoaders/ICU/resources/res-file-list.txt'],
        command: [find_program('gencmn'), '--name', pkgname, '-S', '@OUTPUT@', '-d', '.', '@INPUT@']
    )

    custom_target(
        'root.res',
        output: ['root.res'],
        input: [source_root + 'xercesc/util/MsgLoaders/ICU/resources/root.txt'],
        command: [find_program('genrb'), '-d', '.', '@INPUT']
    )

    custom_target(
        'root_res.c',
        output: ['root_res.c'],
        input: ['root.res'],
        command: [find_program('gencode'), '--name', pkgname, '-d', '.', '@INPUT@']
    )
endif

if msgloaders[0] == 'iconv'
    libxerces_c_sources += msgiconv_sources

    pkgname = 'XercesMessages'

    res_target = pkgname + '_en_US.cat'
    res_file = source_root + '/xercesc/util/MsgLoaders/MsgCatalog/XercesMessages_en_US.Msg'

    custom_target(
        res_target,
        output: [res_target],
        input: [res_file],
        command: [find_program('gencat'), res_target, res_file]
    )

    # TODO: find out why gencat ALL is required
    # TODO: install res_target
endif

# Mutex Managers, conditionally built based on selection
if mutexmgrs[0] == 'nothreads'
    libxerces_c_sources += nothreadmmgr_sources
endif

if mutexmgrs[0] == 'standard'
    libxerces_c_sources += stdmmgr_sources
    libxerces_c_deps += threads_dep
endif

if mutexmgrs[0] == 'posix'
    libxerces_c_sources += posixfmgr_sources
    libxerces_c_deps += threads_dep
endif

if mutexmgrs[0] == 'windows'
    libxerces_c_sources += winmmgr_sources
endif

# File Managers, conditionally built based on selection
if filemgr == 'POSIX'
    libxerces_c_sources += posixfmgr_sources
endif

if filemgr == 'windows'
    libxerces_c_sources += winfmgr_sources
endif

# Windows resource.  With some additional work to clean it up, it
# might be possible to use with Cygwin and MinGW.
if host_system == 'windows'
    windows = import('windows')
    version_rc = windows.compile_resources(
        build_root + '/src/xercesc/util/version.rc',
        args: ['/dXERCES_DLL_NAME="xerces-c\\0"'],
        depend_files: source_root + '/xercesc/util/version.rc.cmake.in')
    libxerces_c_resources += version_rc
endif

# Definitions required for building
add_project_arguments(['-DHAVE_CONFIG_H=1', '-DXERCES_BUILDING_LIBRARY=1'], language:['c', 'cpp'])

# Search the project binary dir for config.h

library('xerces-c',
    sources: libxerces_c_sources + libxerces_c_resources,
    include_directories: include_directories(['..']),
    dependencies: libxerces_c_deps,
)

# TODO: Add windows resource file specific properties
# TODO: Set libtool specific versions
