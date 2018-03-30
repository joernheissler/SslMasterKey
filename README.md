# SslMasterKey

Python module to retrieve the Master Key and Client Random from an `ssl.SSLSocket`.

This can be used to decrypt TLS traffic with [WireShark](https://www.wireshark.org/).
See <https://wiki.wireshark.org/SSL#Using_the_.28Pre.29-Master-Secret> for more details.

## Requirements

  * cpython
  * libssl1.1

## Usage

  * Dump your encrypted traffic into a pcap file.
  * Use `get_ssl_master_key` on your `ssl.SSLSocket`.
  * Write its output (`CLIENT_RANDOM .....`) into a text file.
  * In WireShark in the protocol preferences for SSL, set the "(Pre)-Master-Secret log filename" to this file.
  * Load the pcap file.

## Help wanted

The code is ugly. Please improve it, e.g.:

  * Port it to cffi
  * Add support for other OpenSSL versions
  * Add support for PyPy
