
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
$ ./waf configure --enable-rdp --enable-crc32 --enable-hmac --enable-can-socket --with-os=posix --install-csp --enable-shlib --enable-promisc --enable-xtea --enable-python3-bindings --enable-if-zmqhub --with-driver-usart=linux

Setting top to                           : /media/psf/git/libcsp 
Setting out to                           : /media/psf/git/libcsp/build 
Checking for 'gcc' (C compiler)          : /usr/bin/gcc 
Checking for program 'pkg-config'        : /usr/bin/pkg-config 
Checking for 'libsocketcan'              : yes 
Checking for 'libzmq'                    : yes 
Checking for 'python3'                   : yes 
Checking for endianness                  : little 
'configure' finished successfully (0.084s)
```

Build of libCSP:

```
$ ./waf build

Waf: Entering directory `/media/psf/git/libcsp/build'
[ 1/92] Compiling src/csp_dedup.c
[ 2/92] Compiling src/csp_debug.c
[ 3/92] Compiling src/csp_crc32.c
[ 4/92] Compiling src/csp_conn.c
[ 5/92] Compiling src/csp_buffer.c
[ 6/92] Compiling src/csp_bridge.c
[ 7/92] Compiling src/crypto/csp_xtea.c
[ 8/92] Compiling src/crypto/csp_sha1.c
[ 9/92] Compiling src/interfaces/csp_if_zmqhub.c
[10/92] Compiling src/crypto/csp_hmac.c
[11/92] Compiling src/arch/posix/csp_time.c
[12/92] Compiling src/arch/posix/pthread_queue.c
[13/92] Compiling src/interfaces/csp_if_can_pbuf.c
[14/92] Compiling src/arch/posix/csp_malloc.c
[15/92] Compiling src/transport/csp_udp.c
[16/92] Compiling src/rtable/csp_rtable_static.c
[17/92] Compiling src/csp_io.c
[18/92] Compiling src/interfaces/csp_if_lo.c
[19/92] Compiling src/interfaces/csp_if_i2c.c
[20/92] Compiling src/csp_sfp.c
[21/92] Compiling src/csp_service_handler.c
[22/92] Compiling src/csp_qfifo.c
[23/92] Compiling src/csp_services.c
[24/92] Compiling src/interfaces/csp_if_kiss.c
[25/92] Compiling src/arch/posix/csp_queue.c
[26/92] Compiling src/rtable/csp_rtable.c
[27/92] Compiling src/transport/csp_rdp.c
[28/92] Compiling src/csp_hex_dump.c
[29/92] Compiling src/csp_iflist.c
[30/92] Compiling src/arch/posix/csp_thread.c
[31/92] Compiling src/arch/posix/csp_semaphore.c
[32/92] Compiling src/csp_route.c
[33/92] Compiling src/csp_init.c
[34/92] Compiling src/csp_port.c
[35/92] Compiling src/arch/csp_system.c
[36/92] Compiling src/csp_promisc.c
[37/92] Compiling src/drivers/can/can_socketcan.c
[38/92] Compiling src/arch/posix/csp_system.c
[39/92] Compiling src/arch/csp_time.c
[40/92] Compiling src/drivers/usart/usart_kiss.c
[41/92] Compiling src/drivers/usart/usart_linux.c
[42/92] Compiling src/arch/posix/csp_clock.c
[43/92] Compiling src/interfaces/csp_if_can.c
[44/92] Compiling src/csp_endian.c
[45/92] Compiling src/arch/posix/csp_thread.c
[46/92] Compiling src/interfaces/csp_if_can_pbuf.c
[47/92] Compiling src/csp_services.c
[48/92] Compiling src/arch/posix/csp_malloc.c
[49/92] Compiling src/csp_bridge.c
[50/92] Compiling src/interfaces/csp_if_zmqhub.c
[51/92] Compiling src/csp_endian.c
[52/92] Compiling src/csp_qfifo.c
[53/92] Compiling src/csp_port.c
[54/92] Compiling src/arch/posix/csp_semaphore.c
[55/92] Compiling src/csp_crc32.c
[56/92] Compiling src/transport/csp_rdp.c
[57/92] Compiling src/rtable/csp_rtable_static.c
[58/92] Compiling src/interfaces/csp_if_can.c
[59/92] Linking build/libcsp.so
[60/92] Compiling src/interfaces/csp_if_lo.c
[61/92] Compiling src/arch/posix/csp_queue.c
[62/92] Compiling src/csp_debug.c
[63/92] Compiling src/arch/csp_system.c
[64/92] Compiling src/crypto/csp_hmac.c
[65/92] Compiling src/rtable/csp_rtable.c
[66/92] Compiling src/csp_buffer.c
[67/92] Compiling src/drivers/usart/usart_linux.c
[68/92] Compiling src/csp_hex_dump.c
[69/92] Compiling src/csp_sfp.c
[70/92] Compiling src/arch/posix/pthread_queue.c
[71/92] Compiling src/arch/posix/csp_clock.c
[72/92] Compiling src/csp_conn.c
[73/92] Compiling src/crypto/csp_sha1.c
[74/92] Compiling src/arch/csp_time.c
[75/92] Compiling src/csp_route.c
[76/92] Compiling src/csp_iflist.c
[77/92] Compiling src/csp_dedup.c
[78/92] Compiling src/drivers/usart/usart_kiss.c
[79/92] Compiling src/csp_io.c
[80/92] Compiling src/arch/posix/csp_system.c
[81/92] Compiling src/interfaces/csp_if_kiss.c
[82/92] Compiling src/drivers/can/can_socketcan.c
[83/92] Compiling src/arch/posix/csp_time.c
[84/92] Compiling src/csp_service_handler.c
[85/92] Compiling src/csp_promisc.c
[86/92] Compiling src/transport/csp_udp.c
[87/92] Compiling src/csp_init.c
[88/92] Compiling src/crypto/csp_xtea.c
[89/92] Compiling src/interfaces/csp_if_i2c.c
[90/92] Compiling src/bindings/python/pycsp.c
[91/92] Linking build/libcsp.a
[92/92] Linking build/libcsp_py3.so
Waf: Leaving directory `/media/psf/git/libcsp/build'
'build' finished successfully (1.550s)
```

Install libCSP:

```
$ sudo ./waf install

Waf: Entering directory `/media/psf/git/libcsp/build'
+ install /usr/local/lib/libcsp.so (from build/libcsp.so)
+ install /usr/local/lib/libcsp_py3.so (from build/libcsp_py3.so)
Waf: Leaving directory `/media/psf/git/libcsp/build'
'install' finished successfully (0.169s)
```

```
sudo cp -r include/csp /usr/local/include
sudo cp -r build/include/csp /usr/local/include
sudo cp build/libcsp* /usr/local/lib
```

Build examples:

```
$ ./examples/buildall.py 

$ ./examples/buildall.py 
Waf build command: ['./waf', 'distclean', 'configure', 'build']
'distclean' finished successfully (0.055s)
Setting top to                           : /media/psf/git/libcsp 
Setting out to                           : /media/psf/git/libcsp/build 
Checking for 'gcc' (C compiler)          : /usr/bin/gcc 
Checking for program 'pkg-config'        : /usr/bin/pkg-config 
Checking for 'libsocketcan'              : yes 
Checking for 'libzmq'                    : yes 
Checking for 'python3'                   : yes 
Checking for endianness                  : little 
'configure' finished successfully (0.068s)
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
[13/91] Compiling src/arch/posix/csp_system.c
[14/91] Compiling src/arch/posix/csp_malloc.c
[15/91] Compiling src/arch/posix/csp_clock.c
[16/91] Compiling src/rtable/csp_rtable.c
[17/91] Compiling src/interfaces/csp_if_lo.c
[18/91] Compiling src/interfaces/csp_if_i2c.c
[19/91] Compiling src/interfaces/csp_if_can.c
[20/91] Compiling src/csp_endian.c
[21/91] Compiling src/drivers/usart/usart_linux.c
[22/91] Compiling src/csp_io.c
[23/91] Compiling src/arch/posix/csp_queue.c
[24/91] Compiling src/rtable/csp_rtable_cidr.c
[25/91] Compiling src/csp_hex_dump.c
[26/91] Compiling src/csp_iflist.c
[27/91] Compiling src/transport/csp_rdp.c
[28/91] Compiling src/csp_init.c
[29/91] Compiling src/csp_port.c
[30/91] Compiling src/arch/posix/csp_time.c
[31/91] Compiling src/arch/posix/csp_semaphore.c
[32/91] Compiling src/csp_route.c
[33/91] Compiling src/csp_promisc.c
[34/91] Compiling src/csp_qfifo.c
[35/91] Compiling src/transport/csp_udp.c
[36/91] Compiling src/csp_service_handler.c
[37/91] Compiling src/csp_services.c
[38/91] Compiling src/interfaces/csp_if_can_pbuf.c
[39/91] Compiling src/arch/csp_system.c
[40/91] Compiling src/csp_sfp.c
[41/91] Compiling src/drivers/can/can_socketcan.c
[42/91] Compiling src/arch/csp_time.c
[43/91] Compiling src/drivers/usart/usart_kiss.c
[44/91] Compiling src/interfaces/csp_if_kiss.c
[45/91] Compiling src/bindings/python/pycsp.c
[46/91] Compiling src/arch/csp_time.c
[47/91] Compiling src/csp_crc32.c
[48/91] Compiling src/arch/posix/csp_malloc.c
[49/91] Compiling src/csp_bridge.c
[50/91] Compiling src/interfaces/csp_if_zmqhub.c
[51/91] Compiling src/csp_service_handler.c
[52/91] Compiling src/csp_endian.c
[53/91] Compiling src/arch/posix/csp_semaphore.c
[54/91] Compiling src/crypto/csp_hmac.c
[55/91] Compiling src/csp_port.c
[56/91] Compiling src/transport/csp_rdp.c
[57/91] Compiling src/rtable/csp_rtable_cidr.c
[58/91] Compiling src/csp_qfifo.c
[59/91] Linking build/libcsp.so
[60/91] Compiling src/interfaces/csp_if_can.c
[61/91] Compiling src/arch/posix/csp_queue.c
[62/91] Compiling src/csp_init.c
[63/91] Compiling src/arch/posix/csp_system.c
[64/91] Compiling src/csp_dedup.c
[65/91] Compiling src/interfaces/csp_if_lo.c
[66/91] Compiling src/csp_buffer.c
[67/91] Compiling src/arch/posix/csp_thread.c
[68/91] Compiling src/csp_hex_dump.c
[69/91] Compiling src/interfaces/csp_if_can_pbuf.c
[70/91] Compiling src/arch/posix/pthread_queue.c
[71/91] Compiling src/arch/posix/csp_clock.c
[72/91] Compiling src/csp_debug.c
[73/91] Compiling src/crypto/csp_sha1.c
[74/91] Compiling src/csp_route.c
[75/91] Compiling src/transport/csp_udp.c
[76/91] Compiling src/csp_conn.c
[77/91] Compiling src/arch/posix/csp_time.c
[78/91] Compiling src/drivers/usart/usart_kiss.c
[79/91] Compiling src/csp_sfp.c
[80/91] Linking build/libcsp_py3.so
[81/91] Compiling src/csp_iflist.c
[82/91] Compiling src/interfaces/csp_if_kiss.c
[83/91] Compiling src/drivers/usart/usart_linux.c
[84/91] Compiling src/rtable/csp_rtable.c
[85/91] Compiling src/interfaces/csp_if_i2c.c
[86/91] Compiling src/csp_io.c
[87/91] Compiling src/drivers/can/can_socketcan.c
[88/91] Compiling src/arch/csp_system.c
[89/91] Compiling src/csp_services.c
[90/91] Compiling src/crypto/csp_xtea.c
[91/91] Compiling src/csp_promisc.c
Waf: Leaving directory `/media/psf/git/libcsp/build'
'build' finished successfully (1.324s)
'distclean' finished successfully (0.048s)
Setting top to                           : /media/psf/git/libcsp 
Setting out to                           : /media/psf/git/libcsp/build 
Checking for 'gcc' (C compiler)          : /usr/bin/gcc 
Checking for program 'pkg-config'        : /usr/bin/pkg-config 
Checking for 'libsocketcan'              : yes 
Checking for 'libzmq'                    : yes 
Checking for 'python3'                   : yes 
Checking for endianness                  : little 
'configure' finished successfully (0.072s)
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
[17/98] Compiling src/arch/posix/csp_malloc.c
[18/98] Compiling src/interfaces/csp_if_kiss.c
[19/98] Compiling src/interfaces/csp_if_can_pbuf.c
[20/98] Compiling src/drivers/usart/usart_kiss.c
[21/98] Compiling src/csp_conn.c
[22/98] Compiling src/rtable/csp_rtable_static.c
[23/98] Compiling src/crypto/csp_sha1.c
[24/98] Compiling src/csp_iflist.c
[25/98] Compiling src/drivers/can/can_socketcan.c
[26/98] Compiling src/drivers/usart/usart_linux.c
[27/98] Compiling src/transport/csp_udp.c
[28/98] Compiling src/arch/posix/csp_thread.c
[29/98] Compiling src/csp_crc32.c
[30/98] Compiling src/crypto/csp_xtea.c
[31/98] Compiling src/csp_port.c
[32/98] Compiling src/arch/csp_time.c
[33/98] Compiling src/interfaces/csp_if_can.c
[34/98] Compiling src/csp_debug.c
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
[47/98] Compiling src/drivers/can/can_socketcan.c
[48/98] Compiling src/interfaces/csp_if_i2c.c
[49/98] Compiling src/arch/csp_system.c
[50/98] Compiling src/csp_promisc.c
[51/98] Compiling src/interfaces/csp_if_can_pbuf.c
[52/98] Compiling src/csp_conn.c
[53/98] Compiling src/crypto/csp_sha1.c
[54/98] Compiling src/arch/posix/csp_queue.c
[55/98] Compiling src/interfaces/csp_if_can.c
[56/98] Compiling src/drivers/usart/usart_kiss.c
[57/98] Compiling src/csp_services.c
[58/98] Compiling src/csp_service_handler.c
[59/98] Linking build/libcsp.a
[60/98] Compiling src/arch/posix/csp_clock.c
[61/98] Compiling src/transport/csp_rdp.c
[62/98] Compiling src/csp_endian.c
[63/98] Compiling src/csp_hex_dump.c
[64/98] Compiling src/rtable/csp_rtable_static.c
[65/98] Compiling src/csp_debug.c
[66/98] Compiling src/arch/posix/csp_semaphore.c
[67/98] Compiling src/csp_dedup.c
[68/98] Compiling src/csp_sfp.c
[69/98] Compiling src/csp_route.c
[70/98] Compiling src/csp_crc32.c
[71/98] Compiling src/arch/csp_time.c
[72/98] Compiling src/csp_init.c
[73/98] Compiling src/csp_io.c
[74/98] Compiling src/csp_port.c
[75/98] Compiling src/csp_qfifo.c
[76/98] Compiling src/arch/posix/csp_thread.c
[77/98] Compiling src/arch/posix/pthread_queue.c
[78/98] Compiling src/interfaces/csp_if_zmqhub.c
[79/98] Compiling src/csp_iflist.c
[80/98] Compiling src/rtable/csp_rtable.c
[81/98] Compiling src/interfaces/csp_if_kiss.c
[82/98] Compiling src/csp_bridge.c
[83/98] Compiling src/csp_buffer.c
[84/98] Compiling src/crypto/csp_xtea.c
[85/98] Compiling src/crypto/csp_hmac.c
[86/98] Compiling src/transport/csp_udp.c
[87/98] Compiling src/interfaces/csp_if_lo.c
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
'build' finished successfully (1.626s)
```

# Original documentation

[see here](./README-original.rst)
