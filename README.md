To test building a new sogo version against a new sope, use mock's chain building support:

- `(cd sope && fedpkg srpm)`
- `(cd sogo && fedpkg srpm && fedpkg mock-config >../mock.cfg)`
- `mock -r ./mock.cfg --chain sope/sope*.src.rpm sogo/sogo-*.src.rpm --localrepo results`

To run this in a container, install

- `fedpkg`
- `tito`

and run the container with `--privileged` to allow nested containers.
