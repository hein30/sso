## Travelport WSDL import

Imports WSDLs from the Travelport zip archive to generate web service clients and bean classes.

To build, just run `ant`

To deploy to releases, 
* `cd dist`
* for each subdirectory `travelport-foo`, run `scp travelport-foo/*.* <you>@releases.eysys.com:/srv/releases/travelport-foo/`
* double-check file permissions on the server after doing this


Currently these commands are:
```bash
scp travelport-air/*.* <you>releases.eysys.com:/srv/releases/travelport-air/
scp travelport-gds/*.* <you>@releases.eysys.com:/srv/releases/travelport-gds/
scp travelport-system/*.* <you>@releases.eysys.com:/srv/releases/travelport-system/
scp travelport-universal/*.* <you>@releases.eysys.com:/srv/releases/travelport-universal/
```

To add a new module called travelport-foo:
* copy travelport-air-ivy.xml to travelport-foo-ivy.xml and edit all occurrances of travelport-air in that file to travelport-foo
* add an `<antcall target="dist.module" ...` entry to the `dist` target, setting properties as appropriate

