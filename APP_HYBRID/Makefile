SERIAL_TARGET=optimal_fence_serial
MPI_TARGET=optimal_fence_hybrid

all : serial mpi

bb : $(SERIAL_TARGET) $(MPI_TARGET)

serial : $(SERIAL_TARGET)

$(SERIAL_TARGET) : optimal_fence_serial.c
	gcc optimal_fence_serial.c -lm -o $(SERIAL_TARGET)

mpi : $(MPI_TARGET)

$(MPI_TARGET) : optimal_fence_mpi.cpp
	mpic++ optimal_fence_hybrid.cpp -o $(MPI_TARGET)

run-moore : bb
	./run_all.sh

