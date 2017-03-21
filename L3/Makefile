VHDL=ghdl
VHDL_FLAGS=

OBJ_DIR=./obj
SRC_DIR=./src
GTKWAVE_DIR=./gtkwave

all: simple simple_tb twoway twoway_tb

analyze: simple_tb twoway_tb
	${VHDL} -r simple_tb --vcd=${GTKWAVE_DIR}/simple_tb.vcd
	${VHDL} -r twoway_tb --vcd=${GTKWAVE_DIR}/twoway_tb.vcd

simple:
	${VHDL} -a --workdir=${OBJ_DIR} ${SRC_DIR}/$@.vhdl && \
	${VHDL} -e --workdir=${OBJ_DIR} $@

simple_tb: simple
	${VHDL} -a --workdir=${OBJ_DIR} ${SRC_DIR}/$@.vhdl && \
	${VHDL} -e --workdir=${OBJ_DIR} $@

twoway:
	${VHDL} -a --workdir=${OBJ_DIR} ${SRC_DIR}/$@.vhdl && \
	${VHDL} -e --workdir=${OBJ_DIR} $@

twoway_tb: twoway
	${VHDL} -a --workdir=${OBJ_DIR} ${SRC_DIR}/$@.vhdl && \
	${VHDL} -e --workdir=${OBJ_DIR} $@

clean:
	rm -f ${OBJ_DIR}/*
	rm -f ${GTKWAVE_DIR}/*
	rm -f e~*
	rm -f simple
	rm -f simple_tb
	rm -f twoway
	rm -f twoway_tb
