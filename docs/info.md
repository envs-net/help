# system info

envs is hosted in germany.

builder & maintainer is [creme](https://envs.net/~creme/).

status page: [https://status.envs.net/](https://status.envs.net/)

you can find more info on installed packages on the [sysinfo page](https://envs.net/sysinfo/)<br />
as well as summarized in our [sysinfo.json](https://envs.net/sysinfo.json).

***

## # sshfp

| Algorithm | Fingerprint |
| --- | --- |
| RSA       | `SHA256:7dB470mfzlyhhtqmjnXciIxp+jWLACiYKC3EE/Z0lFg` |
| ECDSA     | `SHA256:U0C6SKGXUflve16m2l4KWBdLLARW6O8TiGWZsXAU2i4` |
| ED25519   | `SHA256:V+mXTsRJ+jfJMxxPlD/28dpWouuns3Wuqwppv6ykVC8` |

## # dns-server
envs.net has her own dns master & slave server and use an additional slave from tildeverse.

| Name | Address | Location | Type |
| --- | --- | --- | --- |
| ns1.envs.net       | `89.163.145.170`             | Düsseldorf  | master |
| ns2.envs.net       | `168.119.12.180`             | Falkenstein | slave  |
| ns2.envs.net       | `2a01:4f8:242:430b:0:a:0:3`  | Falkenstein | slave  |
| | | | |
| ns1.tildeverse.net | `157.90.196.48`              | Falkenstein | slave  |
| ns1.tildeverse.net | `2a01:4f8:252:3e22::48`      | Falkenstein | slave  |

### master-zones:
- envs.net
- envs.sh
