objects = matmul4_4.o matmul8_8.o matmul16_16.o
executables = $(OUT_DIR)/matmul4_4.out $(OUT_DIR)/matmul8_8.out $(OUT_DIR)/matmul16_16.out $(OUT_DIR)/qsort_10.out $(OUT_DIR)/qsort_50.out $(OUT_DIR)/qsort_100.out $(OUT_DIR)/qsort_500.out $(OUT_DIR)/test_1.out
dependancies = src/matmul.c include/matmul.h src/qsort.c include/qsort.h
CCX = riscv32-unknown-elf-gcc
INCLUDE = ./include
OUT_DIR = ./build
all: directories $(executables)
$(OUT_DIR)/matmul4_4.out : $(dependancies)
	$(CCX) -I $(INCLUDE) src/matmul.c -o $(OUT_DIR)/matmul4_4.out -D SIZE=4
$(OUT_DIR)/matmul8_8.out : $(dependancies)
	$(CCX) -I $(INCLUDE) src/matmul.c -o $(OUT_DIR)/matmul8_8.out -D SIZE=8
$(OUT_DIR)/matmul16_16.out : $(dependancies)
	$(CCX) -I $(INCLUDE) src/matmul.c -o $(OUT_DIR)/matmul16_16.out -D SIZE=16
$(OUT_DIR)/qsort_10.out : src/qsort.c include/qsort.h
	$(CCX) -I $(INCLUDE) src/qsort.c -o $(OUT_DIR)/qsort_10.out -D SIZE=10
$(OUT_DIR)/qsort_50.out : src/qsort.c include/qsort.h
	$(CCX) -I $(INCLUDE) src/qsort.c -o $(OUT_DIR)/qsort_50.out -D SIZE=50
$(OUT_DIR)/qsort_100.out : src/qsort.c include/qsort.h
	$(CCX) -I $(INCLUDE) src/qsort.c -o $(OUT_DIR)/qsort_100.out -D SIZE=100
$(OUT_DIR)/qsort_500.out : src/qsort.c include/qsort.h
	$(CCX) -I $(INCLUDE) src/qsort.c -o $(OUT_DIR)/qsort_500.out -D SIZE=500
$(OUT_DIR)/test_1.out : src/test_1.c
	$(CCX) src/test_1.c -o $(OUT_DIR)/test_1.out
directories: ${OUT_DIR}
${OUT_DIR}:
	mkdir -p ${OUT_DIR}
clean:
	rm $(executables)
.PHONY: all clean directories
