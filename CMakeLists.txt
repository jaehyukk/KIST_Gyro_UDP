CXX = g++
CXXFLAGS = -Wall -I../../include
LDFLAGS = -L../../build/bin
LDLIBS = -lvncxx -ljsoncpp -lpthread

SRCS = main.cpp
OBJS = $(SRCS:.cpp=.o)

.PHONY: all clean

all: getting_started

getting_started: $(OBJS)
	$(CXX) $(LDFLAGS) -o $@ $^ $(LDLIBS)

%.o: %.cpp
	$(CXX) $(CXXFLAGS) -c -o $@ $<

clean:
	rm -f getting_started $(OBJS)
