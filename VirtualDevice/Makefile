TARGET  := libVirtualDevice.so
CC      := g++
LIBS    :=
LDFLAGS :=
DEFINES :=
INCLUDE := -I$(OPENNI2_INCLUDE) -I/home/fengping/Downloads/NiTE-Linux-x64-2.2/Include/ \
	-I/home/fengping/Downloads/OpenNI2/ThirdParty/PSCommon/XnLib/Include/
CFLAGS  := -g -Wall -O3 $(DEFINES) $(INCLUDE)
CXXFLAGS:= $(CFLAGS) -DHAVE_CONFIG_H -std=c++11 -fPIC
SHARE   := -shared -o
  
#i think you should do anything here
#下面的基本上不需要做任何改动了
  
#source file
#源文件，自动找所有.c和.cpp文件，并将目标定义为同名.o文件
SOURCE  := $(wildcard *.c) $(wildcard *.cpp)
OBJS    := $(patsubst %.c,%.o,$(patsubst %.cpp,%.o,$(SOURCE)))
  
.PHONY : everything objs clean veryclean rebuild
  
everything : $(TARGET)
  
all : $(TARGET)
  
objs : $(OBJS)
  
rebuild: veryclean everything
                
clean :
	rm -fr *.o
    
veryclean : clean
	rm -fr $(TARGET)
  
$(TARGET) : $(OBJS)
	$(CC) $(CXXFLAGS) $(SHARE) $@ $(OBJS) $(LDFLAGS) $(LIBS)
