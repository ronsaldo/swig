TOP        = ../..
SWIG       = $(TOP)/../preinst-swig
CXXSRCS    = example.cxx
TARGET     = example
INTERFACE  = example.i
LIBS       = -lm
SWIGOPT    = 

check: build
	$(MAKE) -f $(TOP)/Makefile python_run

build:
	$(SWIG) -python -external-runtime
	$(MAKE) -f $(TOP)/Makefile $(SWIGLIB) CXXSRCS='$(CXXSRCS)' SWIG='$(SWIG)' \
	SWIGOPT='$(SWIGOPT)' TARGET='$(TARGET)' INTERFACE='$(INTERFACE)' python_cpp

static:
	$(MAKE) -f $(TOP)/Makefile $(SWIGLIB) CXXSRCS='$(CXXSRCS)' SWIG='$(SWIG)' \
	SWIGOPT='$(SWIGOPT)' TARGET='mypython' INTERFACE='$(INTERFACE)' python_cpp_static

clean:
	$(MAKE) -f $(TOP)/Makefile TARGET='$(TARGET)' python_clean
	rm -f swigpyrun.h
