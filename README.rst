PSRC / SpacecraftAI clone of libCSP v1.6
==========================

Clone the repo:

``
git clone https://github.com/tii-psrc/libcsp.git
cd libcsp/
git checkout psrc2025
``

Install dependencies:

``
sudo apt install libzmq3-dev libsocketcan-dev
``

Configure WAF build tool:

``
$ ./waf configure
Setting top to                           : /media/psf/git/libcsp 
Setting out to                           : /media/psf/git/libcsp/build 
Checking for 'gcc' (C compiler)          : /usr/bin/gcc 
Checking for endianness                  : little 
'configure' finished successfully (0.096s)
``

Build of libCSP:

``
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
``

Build examples:

``
./examples/buildall.py 
``





The Cubesat Space Protocol
==========================

Cubesat Space Protocol (CSP) is a small protocol stack written in C. CSP is designed to ease communication between distributed embedded systems in smaller networks, such as Cubesats. The design follows the TCP/IP model and includes a transport protocol, a routing protocol and several MAC-layer interfaces. The core of `libcsp` includes a router, a connection oriented socket API and message/connection pools.

The protocol is based on a 32-bit header containing both transport and network-layer information. Its implementation is designed for, but not limited to, embedded systems such as the 8-bit AVR microprocessor and the 32-bit ARM and AVR from Atmel. The implementation is written in GNU C and is currently ported to run on FreeRTOS, Linux (POSIX), MacOS and Windows. The primiary platforms being used are FreeRTOS and Linux.

The idea is to give sub-system developers of cubesats the same features of a TCP/IP stack, but without adding the huge overhead of the IP header. The small footprint and simple implementation allows a small 8-bit system to be fully connected on the network. This allows all subsystems to provide their services on the same network level, without any master node required. Using a service oriented architecture has several advantages compared to the traditional mater/slave topology used on many cubesats.

 * Standardised network protocol: All subsystems can communicate with eachother
 * Service loose coupling: Services maintain a relationship that minimizes dependencies between subsystems
 * Service abstraction: Beyond descriptions in the service contract, services hide logic from the outside world
 * Service reusability: Logic is divided into services with the intention of promoting reuse.
 * Service autonomy: Services have control over the logic they encapsulate.
 * Service Redundancy: Easily add redundant services to the bus
 * Reduces single point of failure: The complexity is moved from a single master node to several well defined services on the network

The implementation of `libcsp` is written with simplicity in mind, but it's compile time configuration allows it to have some rather advanced features as well:

Features
--------

 * Thread safe Socket API
 * Router task with Quality of Services
 * Connection-oriented operation (RFC 908 and 1151).
 * Connection-less operation (similar to UDP)
 * ICMP-like requests such as ping and buffer status.
 * Loopback interface
 * Very Small Footprint in regards to code and memory required
 * Zero-copy buffer and queue system
 * Modular network interface system
 * OS abstraction, currently ported to: FreeRTOS, Linux (POSIX), MacOS and Windows
 * Broadcast traffic
 * Promiscuous mode
 * Encrypted packets with XTEA in CTR mode
 * Truncated HMAC-SHA1 Authentication (RFC 2104)

LGPL Software license
---------------------
The source code is available under an LGPL 2.1 license. See COPYING for the license text.

