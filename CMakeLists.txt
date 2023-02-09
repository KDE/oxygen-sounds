# SPDX-FileCopyrightText: 2021 Benjamin Port <benjamin.port@enioka.com>
# SPDX-License-Identifier: BSD-2-Clause

cmake_minimum_required(VERSION 3.16)

project(oxygen-sounds)
set(PROJECT_VERSION "5.27.0")
set(PROJECT_VERSION_MAJOR 5)

include(FeatureSummary)

################# Qt/KDE #################
set(KF5_MIN_VERSION "5.102.0")

find_package(ECM ${KF5_MIN_VERSION} REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH} )

include(KDEInstallDirs)
include(KDECMakeSettings)

file(GLOB _oggfile CONFIGURE_DEPENDS "sounds/*.ogg" )
install(FILES ${_oggfile}
	DESTINATION  ${KDE_INSTALL_SOUNDDIR} )

feature_summary(WHAT ALL INCLUDE_QUIET_PACKAGES FATAL_ON_MISSING_REQUIRED_PACKAGES)
