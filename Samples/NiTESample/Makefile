######################################
#
######################################
#source file
#源文件，自动找所有.c和.cpp文件，并将目标定义为同名.o文件
SOURCE  := $(wildcard *.c) $(wildcard *.cpp)
OBJS    := $(patsubst %.c,%.o,$(patsubst %.cpp,%.o,$(SOURCE)))

$(warning $(SOURCE) $(OBJS))
#target you can change test to what you want
#目标文件名，输入任意你想要的执行文件名
TARGET  := NiteSample
  
#compile and lib parameter
#编译参数
CC      := g++
LIBS    := -L$(OPENNI2_REDIST) -lOpenNI2 -L/home/fengping/Downloads/NiTE-Linux-x64-2.2/Redist/ -lNiTE2 -L/usr/lib/x86_64-linux-gnu/ -lopencv_core -lopencv_imgproc -lopencv_highgui -lopencv_ml
LDFLAGS :=
DEFINES :=
INCLUDE := -I$(OPENNI2_INCLUDE) -I/home/fengping/Downloads/NiTE-Linux-x64-2.2/Include/ \
        -I/usr/include
CFLAGS  := -g -Wall -O3 $(DEFINES) $(INCLUDE)
CXXFLAGS:= $(CFLAGS) -DHAVE_CONFIG_H -std=c++11
  

.PHONY : everything objs clean veryclean rebuild
  
everything : $(TARGET)
  
all : $(TARGET)
  
objs : $(OBJS)
  
rebuild: veryclean everything
                
clean :
	rm -fr *.so
	rm -fr *.o
    
veryclean : clean
	rm -fr $(TARGET)
  
$(TARGET) : $(OBJS)
	$(CC) $(CXXFLAGS) -o $@ $(OBJS) $(LDFLAGS) $(LIBS)
