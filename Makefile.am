EXTRA_DIST = \
	erlmongo.spec \
	README.rdoc \
	LICENSE.txt \
	$(source_files)

erlmongohdrdir = $(ERLANG_INSTALL_LIB_DIR_erlmongo)/include
dist_erlmongohdr_DATA = \
	include/erlmongo.hrl

erlmongobindir = $(ERLANG_INSTALL_LIB_DIR_erlmongo)/ebin

source_files = \
	src/erlmongo_app.erl \
	src/mongoapi.erl \
	src/mongodb.erl \
	src/erlmongo.app
	src/mongodb_supervisor.erl

beam_files = $(foreach B,$(notdir $(source_files:.erl=.beam)),ebin/$(B))

erlmongobin_DATA = \
	$(beam_files)

CLEANFILES = $(beam_files)

all-rebar: deps build

deps-rebar:
	rebar get-deps
	rebar update-deps

build:
	rebar compile

clean:
	rebar clean
