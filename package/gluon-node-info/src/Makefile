all: announce.so

CFLAGS += -Wall

announce.so: announce.c
	$(CC) $(CPPFLAGS) $(CFLAGS) $(LDFLAGS) -shared -fPIC -D_GNU_SOURCE -o $@ $^ $(LDLIBS) -lgluon -luci
