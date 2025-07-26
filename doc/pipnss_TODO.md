# TODO: Integrate pipnss.properties

The upstream Mozilla codebase includes localization files under
`security/manager/locales/*/chrome/pipnss/pipnss.properties` that provide
certificate dump strings. This repository currently lacks that file. When the
localization files are imported, make sure to append GOST specific strings:

```
#ifdef NSS_ENABLE_GOST
CertDumpGostR3410_2001=GOST R 34.10-2001
CertDumpGostR3411_94_With_GostR3410_2001=GOST R 34.11-94 with GOST R 34.10-2001
#endif
```

These entries enable proper display of certificates using the GOST algorithms.
