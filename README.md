
# PSRC / SpacecraftAI clone of libCSP v1.6

Clone the repo:

```
git clone https://github.com/tii-psrc/libcsp.git
cd libcsp/
git checkout psrc2025
```

Install dependencies:

```
sudo apt install python-is-python3 libzmq3-dev libsocketcan-dev
```

Configure WAF build tool:

```
$ ./waf configure
Setting top to                           : /media/psf/git/libcsp 
Setting out to                           : /media/psf/git/libcsp/build 
Checking for 'gcc' (C compiler)          : /usr/bin/gcc 
Checking for endianness                  : little 
'configure' finished successfully (0.096s)
```

Build of libCSP:

```
$ ./waf build install
Waf: Entering directory `/media/psf/git/libcsp/build'
[ 1/42] Compiling src/csp_sfp.c
[ 2/42] Compiling src/csp_buffer.c
[ 3/42] Compiling src/arch/posix/csp_system.c
[ 4/42] Compiling src/arch/posix/csp_clock.c
[ 5/42] Compiling src/arch/csp_system.c
[ 6/42] Compiling src/csp_endian.c
[ 7/42] Compiling src/transport/csp_rdp.c
[ 8/42] Compiling src/arch/posix/csp_malloc.c
[ 9/42] Compiling src/rtable/csp_rtable.c
[10/42] Compiling src/csp_debug.c
[11/42] Compiling src/arch/posix/csp_thread.c
[12/42] Compiling src/csp_services.c
[13/42] Compiling src/interfaces/csp_if_can.c
[14/42] Compiling src/csp_bridge.c
[15/42] Compiling src/arch/posix/csp_semaphore.c
[16/42] Compiling src/arch/posix/csp_time.c
[17/42] Compiling src/csp_crc32.c
[18/42] Compiling src/interfaces/csp_if_can_pbuf.c
[19/42] Compiling src/rtable/csp_rtable_static.c
[20/42] Compiling src/csp_init.c
[21/42] Compiling src/crypto/csp_hmac.c
[22/42] Compiling src/interfaces/csp_if_kiss.c
[23/42] Compiling src/csp_qfifo.c
[24/42] Compiling src/csp_dedup.c
[25/42] Compiling src/csp_hex_dump.c
[26/42] Compiling src/arch/posix/csp_queue.c
[27/42] Compiling src/csp_port.c
[28/42] Compiling src/crypto/csp_xtea.c
[29/42] Compiling src/csp_service_handler.c
[30/42] Compiling src/transport/csp_udp.c
[31/42] Compiling src/interfaces/csp_if_zmqhub.c
[32/42] Compiling src/arch/posix/pthread_queue.c
[33/42] Compiling src/csp_iflist.c
[34/42] Compiling src/arch/csp_time.c
[35/42] Compiling src/csp_io.c
[36/42] Compiling src/crypto/csp_sha1.c
[37/42] Compiling src/csp_route.c
[38/42] Compiling src/csp_promisc.c
[39/42] Compiling src/csp_conn.c
[40/42] Compiling src/interfaces/csp_if_lo.c
[41/42] Compiling src/interfaces/csp_if_i2c.c
[42/42] Linking build/libcsp.a
Waf: Leaving directory `/media/psf/git/libcsp/build'
'build' finished successfully (0.744s)
Waf: Entering directory `/media/psf/git/libcsp/build'
Waf: Leaving directory `/media/psf/git/libcsp/build'
'install' finished successfully (0.076s)
```

Build examples:

```
./examples/buildall.py 
```

# Original documentation

[see here](./README-original.rst)
