cmake_minimum_required(VERSION 3.16)

project(oxygen-sounds)
set(PROJECT_VERSION "5.23.80")
set(PROJECT_VERSION_MAJOR 5)

include(FeatureSummary)

################# Qt/KDE #################
set(QT_MIN_VERSION "5.15.0")
set(KF5_MIN_VERSION "5.86")
set(KDE_COMPILERSETTINGS_LEVEL "5.82")

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(ECM ${KF5_MIN_VERSION} REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH} )


include(KDEInstallDirs)
include(KDECMakeSettings)
include(KDECompilerSettings NO_POLICY_SCOPE)

FILE(GLOB _oggfile "sounds/*.ogg" )
install(FILES ${_oggfile}
	DESTINATION  ${KDE_INSTALL_SOUNDDIR} )

feature_summary(WHAT ALL INCLUDE_QUIET_PACKAGES FATAL_ON_MISSING_REQUIRED_PACKAGES)
