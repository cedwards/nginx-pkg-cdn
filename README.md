# Bastille Template: nginx-pkg-cdn

Usage:
```shell
bastille bootstrap https://github.com/cedwards/nginx-pkg-cdn
bastille create nginx-pkg-cdn 11.2-RELEASE 10.88.9.40
bastille start nginx-pkg-cdn
bastille template nginx-pkg-cdn cedwards/nginx-pkg-cdn
```

Once created and running, any other jail(s) on the same system can use the
following:

**/usr/local/etc/pkg/repos/cdn.bastillebsd.org.conf**

```shell
cdn.bastillebsd.org: {
  url: "pkg+http://cdn.bastillebsd.org/${ABI}/latest",
  mirror_type: "srv",
  signature_type: "fingerprints",
  fingerprints: "/usr/share/keys/pkg",
  enabled: yes
}
```

**/usr/local/etc/pkg/repos/FreeBSD.conf**

```shell
FreeBSD: { enabled: no }
```
