# system info

envs is hosted in germany.

builder & maintainer is [creme](https://envs.net/~creme/).

status page: [https://status.envs.net/](https://status.envs.net/)

more infos over the installed packages can you find on the [sysinfo page](https://envs.net/sysinfo/)<br />
as well as summarized in our [sysinfo.json](https://envs.net/sysinfo.json).

## # sshfp

| Algorithm | Fingerprint |
| --- | --- |
| RSA       | `SHA256:7dB470mfzlyhhtqmjnXciIxp+jWLACiYKC3EE/Z0lFg` |
| ECDSA     | `SHA256:U0C6SKGXUflve16m2l4KWBdLLARW6O8TiGWZsXAU2i4` |
| ED25519   | `SHA256:V+mXTsRJ+jfJMxxPlD/28dpWouuns3Wuqwppv6ykVC8` |

## # dns-server
envs.net has her own dns master & slave server and use a additional slave from tildeverse.

| Name | Address | Location | Type |
| --- | --- | --- | --- |
| ns1.envs.net       | 89.163.145.170         | Düsseldorf  | master |
| ns2.envs.net       | 168.119.12.180         | Falkenstein | slave  |
| | | | |
| ns1.tildeverse.net | 198.50.128.75          | Montréal    | slave  |
| ns1.tildeverse.net | 2607:5300:203:5fd5::75 | Montréal    | slave  |

### master-zones:
- envs.net
- envs.sh
- envs.o
- envs.tilde

### slave server for:
- tildeverse.org / tildeverse.net
- tilde.team
    - ttm.sh
    - and some more aliases
