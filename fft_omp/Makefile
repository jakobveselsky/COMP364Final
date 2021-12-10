COMMON	= ../common

DBG      ?= -g
CXX	 ?= g++
MPICXX   ?= mpicxx
CXXFLAGS  = -O3 -fopenmp -std=c++11 -I. -I$(COMMON) $(DBG)

EXEC = fft_omp

all: $(EXEC)

OBJS = $(EXEC:=.o)
DEPS = $(OBJS:.o=.d)

-include $(DEPS)

# Load common make options
include $(COMMON)/Makefile.common
LDFLAGS	= $(COMMON_LIBS)

fft_omp: fft_omp.cpp $(COMMON_OBJS)
	$(CXX) $(CXXFLAGS) -o fft_omp $^ $(LDFLAGS)

clean: clean_common
	/bin/rm -fv $(EXEC) *.d *.o *.optrpt
