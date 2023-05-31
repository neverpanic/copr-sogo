To test building a new sogo version against a new sope, use mock's chain building support:

- `(cd sope && fedpkg srpm)`
- `(cd sogo && fedpkg srpm && fedpkg mock-config >../mock.cfg)`
- `mock -r mock --chain sope/sope*.src.rpm sogo/sogo-*.src.rpm --localrepo results`
