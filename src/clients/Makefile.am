CLEANFILES = *~
MAINTAINERCLEANFILES = Makefile.in

AM_CXXFLAGS = -I$(top_srcdir) -std=c++0x -Wall -Wextra -pedantic

bin_PROGRAMS = \
	eos-evaluate \
	eos-list-parameters \
	eos-print-polynomial \
	eos-propagate-uncertainty \
	eos-sample-mcmc \
	eos-sample-events-mcmc \
	eos-scan-mc
noinst_PROGRAMS = \
	integrated \
	observables

LDADD = \
	-lhdf5 \
	$(top_builddir)/eos/statistics/libeosstatistics.la \
	$(top_builddir)/eos/utils/libeosutils.la \
	$(top_builddir)/eos/form-factors/libeosformfactors.la \
	$(top_builddir)/eos/b-decays/libeosbdecays.la \
	$(top_builddir)/eos/rare-b-decays/libeosrarebdecays.la \
	$(top_builddir)/eos/libeos.la

if EOS_ENABLE_PMC
LDADD += \
	-lpmc -ldl
endif

eos_evaluate_SOURCES = eos-evaluate.cc

eos_list_parameters_SOURCES = eos-list-parameters.cc

eos_print_polynomial_SOURCES = eos-print-polynomial.cc

eos_propagate_uncertainty_SOURCES = eos-propagate-uncertainty.cc

eos_sample_mcmc_SOURCES = eos-sample-mcmc.cc

eos_sample_events_mcmc_SOURCES = eos-sample-events-mcmc.cc

eos_scan_mc_SOURCES = eos-scan-mc.cc
eos_scan_mc_LDADD = $(LDADD) -lgsl -lMinuit2

integrated_SOURCES = integrated.cc

observables_SOURCES = observables.cc
