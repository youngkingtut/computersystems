CXX	=g++
CXXFLAGS= -O3
CXXDEBUGFLAGS = -m32 -g -O0 -fno-omit-frame-pointer

goals: judge
	echo "Done"

filter: FilterMain.cpp Filter.cpp cs1300bmp.cc
	$(CXX) $(CXXFLAGS) -o filter FilterMain.cpp Filter.cpp cs1300bmp.cc

filter-debug: FilterMain.cpp Filter.cpp cs1300bmp.cc
	$(CXX) $(CXXDEBUGFLAGS) -o filter FilterMain.cpp Filter.cpp cs1300bmp.cc
##
## Parameters for the test run
##
FILTERS = gauss.filter vline.filter hline.filter emboss.filter
IMAGES = boats.bmp blocks-small.bmp
TRIALS = 1 2 3 4

judge: filter
	-./Judge -p ./filter -i boats.bmp -l storz-boats
	-./Judge -p ./filter -i blocks-small.bmp -l storz-blocks 

clean:
	-rm filter
	-rm filtered-*.bmp

debug: FilterMain.cpp Filter.cpp cs1300bmp.cc
	$(CXX) $(CXXDEBUGFLAGS) -o filter FilterMain.cpp Filter.cpp cs1300bmp.cc
