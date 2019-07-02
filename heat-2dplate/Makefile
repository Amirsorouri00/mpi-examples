CC      := mpicc
CCFLAGS := -I
LDFLAGS := -lX11

TARGETS:= mpi-heat2D
MAINS  := $(addsuffix .o, $(TARGETS) )
OBJ    := draw_heat.o #kbd.o command.o display.o $(MAINS)
DEPS   := #defs.h command.h

BUILDPATH	:= ./build/

.PHONY: all clean

all: $(TARGETS)

clean:
	rm -f $(TARGETS) $(OBJ)

$(OBJ): %.o : %.c $(DEPS)
	$(CC) -c -o $@ $< $(CCFLAGS)

$(TARGETS): % : $(filter-out $(MAINS), $(OBJ)) %.o
	$(CC) -o $@ $(LIBS) $^ $(CCFLAGS) $(BUILDPATH) $(LDFLAGS)
	echo Build Done
