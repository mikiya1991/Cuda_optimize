CPPFLAGS:= -I . -std=c++11 
TARGETS:=$(patsubst %.cpp, %, $(wildcard *.cpp))

all: $(TARGETS)

clean:
	-rm -rf *.o 
	-rm $(TARGETS) 

clean-all: clean
	-rm *.csv *.db *.json *.txt

$(TARGETS): % : %.o
	hipcc $^ -o $@

%.o: %.cpp
	hipcc $(CPPFLAGS) -c $^ -o $@
