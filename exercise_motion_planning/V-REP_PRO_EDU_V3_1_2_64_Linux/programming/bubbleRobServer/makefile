OBJS = simpleInConnection.o simplePorting.o bubbleRobServer.o
OUTPUT = bin/bubbleRobServer
OS = $(shell uname -s)
ECHO = @

ifeq ($(OS), Linux)
	CFLAGS += -D__linux
else
	CFLAGS += -D__APPLE__
endif

all: $(OBJS)
		@mkdir -p bin
		@echo "Linking $(OBJS) to $(OUTPUT)"
		$(ECHO)$(CXX) $(CFLAGS) $(OBJS) -o $(OUTPUT) $(LDFLAGS)

%.o: %.cpp
		@echo "Compiling $< to $@"
		$(ECHO)$(CXX) $(CFLAGS) -c $< -o $@

%.o: %.c
		@echo "Compiling $< to $@" 
		$(ECHO)$(CC) $(CFLAGS) -c $< -o $@

clean:
		@rm -f $(OBJS) bin/bubbleRobServer
