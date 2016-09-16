## SSO connector WSDL import

Imports WSDLs from the Bond SSO endpoints to generate web service clients and bean classes.

To build, just run `ant`

To deploy to releases, 
* `cd dist`
* for each subdirectory `sso-wsdl`, run `scp sso-wsdl/*.* <you>@releases.eysys.com:/srv/releases/sso-wsdl/`
* double-check file permissions on the server after doing this


Currently these commands are:
```bash
scp sso-wsdl/*.* <you>@releases.eysys.com:/srv/releases/sso-wsdl/
```

To add a new module called sso-wsdl2:
* copy sso-wsdl-ivy.xml to sso-wsdl2-ivy.xml and edit all occurrances of sso-wsdl in that file to sso-wsdl2
* add an `<antcall target="dist.module" ...` entry to the `dist` target, setting properties as appropriate

