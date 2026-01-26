
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

Waf build command: ['./waf', 'distclean', 'configure', 'build']
'distclean' finished successfully (0.034s)
Setting top to                           : /media/psf/git/libcsp 
Setting out to                           : /media/psf/git/libcsp/build 
Checking for 'gcc' (C compiler)          : /usr/bin/gcc 
Checking for program 'pkg-config'        : /usr/bin/pkg-config 
Checking for 'libsocketcan'              : yes 
Checking for 'libzmq'                    : yes 
Checking for 'python3'                   : yes 
Checking for endianness                  : little 
'configure' finished successfully (0.077s)
Waf: Entering directory `/media/psf/git/libcsp/build'
[ 1/91] Compiling src/csp_dedup.c
[ 2/91] Compiling src/csp_debug.c
[ 3/91] Compiling src/csp_crc32.c
[ 4/91] Compiling src/csp_conn.c
[ 5/91] Compiling src/csp_buffer.c
[ 6/91] Compiling src/csp_bridge.c
[ 7/91] Compiling src/crypto/csp_xtea.c
[ 8/91] Compiling src/crypto/csp_sha1.c
[ 9/91] Compiling src/interfaces/csp_if_zmqhub.c
[10/91] Compiling src/crypto/csp_hmac.c
[11/91] Compiling src/arch/posix/pthread_queue.c
[12/91] Compiling src/arch/posix/csp_thread.c
[13/91] Compiling src/interfaces/csp_if_can_pbuf.c
[14/91] Compiling src/arch/posix/csp_malloc.c
[15/91] Compiling src/transport/csp_udp.c
[16/91] Compiling src/rtable/csp_rtable.c
[17/91] Compiling src/csp_io.c
[18/91] Compiling src/interfaces/csp_if_kiss.c
[19/91] Compiling src/drivers/usart/usart_linux.c
[20/91] Compiling src/drivers/can/can_socketcan.c
[21/91] Compiling src/csp_services.c
[22/91] Compiling src/csp_hex_dump.c
[23/91] Compiling src/interfaces/csp_if_lo.c
[24/91] Compiling src/arch/posix/csp_queue.c
[25/91] Compiling src/rtable/csp_rtable_cidr.c
[26/91] Compiling src/csp_iflist.c
[27/91] Compiling src/transport/csp_rdp.c
[28/91] Compiling src/csp_init.c
[29/91] Compiling src/csp_port.c
[30/91] Compiling src/arch/posix/csp_time.c
[31/91] Compiling src/arch/posix/csp_semaphore.c
[32/91] Compiling src/csp_route.c
[33/91] Compiling src/csp_promisc.c
[34/91] Compiling src/csp_qfifo.c
[35/91] Compiling src/arch/csp_system.c
[36/91] Compiling src/csp_service_handler.c
[37/91] Compiling src/csp_sfp.c
[38/91] Compiling src/arch/posix/csp_system.c
[39/91] Compiling src/arch/csp_time.c
[40/91] Compiling src/drivers/usart/usart_kiss.c
[41/91] Compiling src/interfaces/csp_if_can.c
[42/91] Compiling src/arch/posix/csp_clock.c
[43/91] Compiling src/csp_endian.c
[44/91] Compiling src/interfaces/csp_if_i2c.c
[45/91] Compiling src/bindings/python/pycsp.c
[46/91] Compiling src/rtable/csp_rtable.c
[47/91] Compiling src/arch/posix/csp_thread.c
[48/91] Compiling src/drivers/usart/usart_linux.c
[49/91] Compiling src/csp_bridge.c
[50/91] Compiling src/interfaces/csp_if_zmqhub.c
[51/91] Compiling src/csp_service_handler.c
[52/91] Compiling src/csp_endian.c
[53/91] Compiling src/arch/posix/csp_semaphore.c
[54/91] Compiling src/csp_port.c
[55/91] Linking build/libcsp.so
[56/91] Compiling src/crypto/csp_hmac.c
[57/91] Compiling src/transport/csp_rdp.c
[58/91] Compiling src/rtable/csp_rtable_cidr.c
[59/91] Compiling src/arch/csp_time.c
[60/91] Compiling src/interfaces/csp_if_can.c
[61/91] Compiling src/arch/posix/csp_queue.c
[62/91] Compiling src/csp_init.c
[63/91] Compiling src/interfaces/csp_if_lo.c
[64/91] Compiling src/csp_conn.c
[65/91] Compiling src/csp_qfifo.c
[66/91] Compiling src/csp_buffer.c
[67/91] Compiling src/csp_sfp.c
[68/91] Compiling src/arch/posix/csp_malloc.c
[69/91] Compiling src/interfaces/csp_if_can_pbuf.c
[70/91] Compiling src/arch/posix/pthread_queue.c
[71/91] Compiling src/arch/posix/csp_clock.c
[72/91] Compiling src/csp_debug.c
[73/91] Compiling src/crypto/csp_sha1.c
[74/91] Linking build/libcsp_py3.so
[75/91] Compiling src/transport/csp_udp.c
[76/91] Compiling src/csp_iflist.c
[77/91] Compiling src/csp_dedup.c
[78/91] Compiling src/csp_io.c
[79/91] Compiling src/drivers/usart/usart_kiss.c
[80/91] Compiling src/arch/posix/csp_system.c
[81/91] Compiling src/csp_crc32.c
[82/91] Compiling src/csp_hex_dump.c
[83/91] Compiling src/interfaces/csp_if_kiss.c
[84/91] Compiling src/arch/posix/csp_time.c
[85/91] Compiling src/interfaces/csp_if_i2c.c
[86/91] Compiling src/csp_promisc.c
[87/91] Compiling src/drivers/can/can_socketcan.c
[88/91] Compiling src/arch/csp_system.c
[89/91] Compiling src/csp_services.c
[90/91] Compiling src/csp_route.c
[91/91] Compiling src/crypto/csp_xtea.c
Waf: Leaving directory `/media/psf/git/libcsp/build'
'build' finished successfully (1.388s)
'distclean' finished successfully (0.046s)
Setting top to                           : /media/psf/git/libcsp 
Setting out to                           : /media/psf/git/libcsp/build 
Checking for 'gcc' (C compiler)          : /usr/bin/gcc 
Checking for program 'pkg-config'        : /usr/bin/pkg-config 
Checking for 'libsocketcan'              : yes 
Checking for 'libzmq'                    : yes 
Checking for 'python3'                   : yes 
Checking for endianness                  : little 
'configure' finished successfully (0.069s)
Waf: Entering directory `/media/psf/git/libcsp/build'
[ 1/98] Compiling src/csp_sfp.c
[ 2/98] Compiling src/csp_buffer.c
[ 3/98] Compiling src/arch/posix/csp_system.c
[ 4/98] Compiling src/arch/posix/csp_clock.c
[ 5/98] Compiling src/arch/csp_system.c
[ 6/98] Compiling src/csp_services.c
[ 7/98] Compiling src/csp_service_handler.c
[ 8/98] Compiling src/csp_bridge.c
[ 9/98] Compiling src/csp_route.c
[10/98] Compiling src/csp_qfifo.c
[11/98] Compiling src/arch/posix/csp_semaphore.c
[12/98] Compiling src/csp_io.c
[13/98] Compiling src/transport/csp_rdp.c
[14/98] Compiling src/csp_hex_dump.c
[15/98] Compiling src/arch/posix/pthread_queue.c
[16/98] Compiling src/rtable/csp_rtable.c
[17/98] Compiling src/interfaces/csp_if_kiss.c
[18/98] Compiling src/arch/posix/csp_malloc.c
[19/98] Compiling src/csp_debug.c
[20/98] Compiling src/drivers/usart/usart_linux.c
[21/98] Compiling src/csp_conn.c
[22/98] Compiling src/rtable/csp_rtable_static.c
[23/98] Compiling src/crypto/csp_sha1.c
[24/98] Compiling src/csp_iflist.c
[25/98] Compiling src/drivers/can/can_socketcan.c
[26/98] Compiling src/drivers/usart/usart_kiss.c
[27/98] Compiling src/transport/csp_udp.c
[28/98] Compiling src/arch/posix/csp_thread.c
[29/98] Compiling src/csp_crc32.c
[30/98] Compiling src/crypto/csp_xtea.c
[31/98] Compiling src/csp_port.c
[32/98] Compiling src/arch/csp_time.c
[33/98] Compiling src/interfaces/csp_if_can.c
[34/98] Compiling src/interfaces/csp_if_can_pbuf.c
[35/98] Compiling src/arch/posix/csp_queue.c
[36/98] Compiling src/interfaces/csp_if_i2c.c
[37/98] Compiling src/arch/posix/csp_time.c
[38/98] Compiling src/csp_promisc.c
[39/98] Compiling src/crypto/csp_hmac.c
[40/98] Compiling src/csp_dedup.c
[41/98] Compiling src/interfaces/csp_if_lo.c
[42/98] Compiling src/csp_init.c
[43/98] Compiling src/interfaces/csp_if_zmqhub.c
[44/98] Compiling src/csp_endian.c
[45/98] Compiling src/drivers/usart/usart_linux.c
[46/98] Compiling src/arch/posix/csp_malloc.c
[47/98] Compiling src/arch/csp_time.c
[48/98] Compiling src/csp_buffer.c
[49/98] Compiling src/csp_qfifo.c
[50/98] Compiling src/csp_promisc.c
[51/98] Compiling src/interfaces/csp_if_can_pbuf.c
[52/98] Compiling src/csp_conn.c
[53/98] Compiling src/crypto/csp_sha1.c
[54/98] Compiling src/interfaces/csp_if_can.c
[55/98] Compiling src/arch/posix/csp_clock.c
[56/98] Compiling src/drivers/usart/usart_kiss.c
[57/98] Compiling src/csp_services.c
[58/98] Compiling src/csp_service_handler.c
[59/98] Compiling src/csp_hex_dump.c
[60/98] Compiling src/transport/csp_rdp.c
[61/98] Compiling src/csp_endian.c
[62/98] Linking build/libcsp.a
[63/98] Compiling src/csp_iflist.c
[64/98] Compiling src/rtable/csp_rtable_static.c
[65/98] Compiling src/csp_debug.c
[66/98] Compiling src/csp_dedup.c
[67/98] Compiling src/arch/posix/csp_semaphore.c
[68/98] Compiling src/csp_sfp.c
[69/98] Compiling src/csp_init.c
[70/98] Compiling src/csp_crc32.c
[71/98] Compiling src/drivers/can/can_socketcan.c
[72/98] Compiling src/csp_route.c
[73/98] Compiling src/csp_io.c
[74/98] Compiling src/csp_port.c
[75/98] Compiling src/arch/csp_system.c
[76/98] Compiling src/crypto/csp_xtea.c
[77/98] Compiling src/arch/posix/pthread_queue.c
[78/98] Compiling src/interfaces/csp_if_zmqhub.c
[79/98] Compiling src/arch/posix/csp_queue.c
[80/98] Compiling src/interfaces/csp_if_lo.c
[81/98] Compiling src/interfaces/csp_if_kiss.c
[82/98] Compiling src/interfaces/csp_if_i2c.c
[83/98] Compiling src/csp_bridge.c
[84/98] Compiling src/arch/posix/csp_thread.c
[85/98] Compiling src/crypto/csp_hmac.c
[86/98] Compiling src/transport/csp_udp.c
[87/98] Compiling src/rtable/csp_rtable.c
[88/98] Compiling src/arch/posix/csp_system.c
[89/98] Compiling src/arch/posix/csp_time.c
[90/98] Compiling src/bindings/python/pycsp.c
[91/98] Compiling examples/csp_server_client.c
[92/98] Compiling examples/csp_arch.c
[93/98] Compiling examples/zmqproxy.c
[94/98] Linking build/libcsp.so
[95/98] Linking build/zmqproxy
[96/98] Linking build/csp_server_client
[97/98] Linking build/csp_arch
[98/98] Linking build/libcsp_py3.so
Waf: Leaving directory `/media/psf/git/libcsp/build'
'build' finished successfully (1.583s)
```

# Original documentation

[see here](./README-original.rst)
