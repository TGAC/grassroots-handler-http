NAME 		= http_handler
DIR_BUILD :=  $(realpath $(dir $(lastword $(MAKEFILE_LIST))))
DIR_SRC := $(realpath $(DIR_BUILD)/../../src)
DIR_INCLUDE := $(realpath $(DIR_BUILD)/../../include)
COMP		= gcc
LINK		= ld
MAKEDEPEND 	= gcc -MM -MF


ifeq ($(DIR_BUILD_UTILS),)
export DIR_BUILD_UTILS = $(realpath $(DIR_BUILD)/../../../../build_utils/linux)
endif
include $(DIR_BUILD_UTILS)/project.properties

export DIR_INSTALL=$(DIR_GRASSROOTS_INSTALL)/handlers

VPATH	= \
	$(DIR_SRC) 	

INCLUDES = \
	-I$(DIR_INCLUDE) \
	-I$(DIR_JANSSON_INC) \
	-I$(DIR_GRASSROOTS_UTIL_INC) \
	-I$(DIR_GRASSROOTS_UTIL_INC)/containers \
	-I$(DIR_GRASSROOTS_UTIL_INC)/io \
	-I$(DIR_GRASSROOTS_HANDLER_INC) \
	-I$(DIR_GRASSROOTS_NETWORK_INC) \
	-I$(DIR_GRASSROOTS_PARAMS_INC) \
	-I$(DIR_GRASSROOTS_SERVICE_INC)

	
SRCS 	= \
	http_handler.c
	
CPPFLAGS = -DUNIX -DHTTP_HANDLER_EXPORTS

LDFLAGS += \
	-L$(DIR_GRASSROOTS_HANDLE_LIB) -l$(GRASSROOTS_HANDLE_LIB_NAME) \

include $(DIR_BUILD_UTILS)/generic_makefiles/shared_library.makefile


