#
# Defines the part type that this project uses.
#
PART=__MSP432P401R__

#
# The base directory for MSPWare.
#
ROOT=../../../..

#
# Include the common make definitions.
#
include ../../Makefile.defs

#
# Where to find header files that do not live in the source directory.
#
IPATH=../../../..
IPATH+=../../../../inc/
IPATH+=../../../../inc/CMSIS/
IPATH+=../../../../driverlib/MSP432P4xx

#
# The default rule, which causes the pcm_lpm45_no_wakeup example to be built.
#
all: ${COMPILER}
all: ${COMPILER}/pcm_lpm45_no_wakeup.axf

#
# The rule to clean out all the build products.
#
clean:
	@rm -rf ${COMPILER} ${wildcard *~}

#
# The rule to create the target directory.
#
${COMPILER}:
	@mkdir -p ${COMPILER}

#
# Rules for building the pcm_lpm45_no_wakeup example.
#
${COMPILER}/pcm_lpm45_no_wakeup.axf: ${COMPILER}/startup_msp432p401r_${COMPILER}.o
${COMPILER}/pcm_lpm45_no_wakeup.axf: ${COMPILER}/system_msp432p401r.o
${COMPILER}/pcm_lpm45_no_wakeup.axf: ${COMPILER}/pcm_lpm45_no_wakeup.o
${COMPILER}/pcm_lpm45_no_wakeup.axf: ${ROOT}/driverlib/MSP432P4xx/${COMPILER}/msp432p4xx_driverlib.a
${COMPILER}/pcm_lpm45_no_wakeup.axf: pcm_lpm45_no_wakeup_gcc.ld
SCATTERgcc_pcm_lpm45_no_wakeup=pcm_lpm45_no_wakeup_gcc.ld
ENTRY_pcm_lpm45_no_wakeup=resetISR
CFLAGSgcc=-DTARGET_IS_MSP432P4XX

#
# Include the automatically generated dependency files.
#
ifneq (${MAKECMDGOALS},clean)
-include ${wildcard ${COMPILER}/*.d} __dummy__
endif
