NAME 		:= http_handler
DIR_BUILD :=  $(realpath $(dir $(lastword $(MAKEFILE_LIST))))
DIR_SRC := $(realpath $(DIR_BUILD)/../../src)
DIR_INCLUDE := $(realpath $(DIR_BUILD)/../../include)

ifeq ($(DIR_BUILD_CONFIG),)
export DIR_BUILD_CONFIG := $(realpath $(DIR_BUILD)/../../../../build-config/linux)
endif

include $(DIR_BUILD_CONFIG)/project.properties

export DIR_INSTALL := $(DIR_GRASSROOTS_INSTALL)/handlers

VPATH	:= \
	$(DIR_SRC) 	

INCLUDES = \
	-I$(DIR_INCLUDE) \
	-I$(DIR_JANSSON_INC) \
	-I$(DIR_UUID_INC) \
	-I$(DIR_GRASSROOTS_UUID_INC) \
	-I$(DIR_GRASSROOTS_SERVER_INC) \
	-I$(DIR_GRASSROOTS_UTIL_INC) \
	-I$(DIR_GRASSROOTS_UTIL_INC)/containers \
	-I$(DIR_GRASSROOTS_UTIL_INC)/io \
	-I$(DIR_GRASSROOTS_HANDLER_INC) \
	-I$(DIR_GRASSROOTS_NETWORK_INC) \
	-I$(DIR_GRASSROOTS_PARAMS_INC) \
	-I$(DIR_GRASSROOTS_SERVICE_INC)

	
SRCS 	:= \
	http_handler.c
	
CPPFLAGS := -DUNIX -DHTTP_HANDLER_EXPORTS

LDFLAGS += \
	-L$(DIR_GRASSROOTS_HANDLE_LIB) -l$(GRASSROOTS_HANDLE_LIB_NAME) \
	-L$(DIR_GRASSROOTS_UUID_LIB) -l$(GRASSROOTS_UUID_LIB_NAME) \

include $(DIR_BUILD_CONFIG)/generic_makefiles/shared_library.makefile


