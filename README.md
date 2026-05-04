To test building a new sogo version against a new sope, use mock's chain building support:

- `(cd sope && fedpkg srpm)`
- `(cd sogo && fedpkg srpm && fedpkg mock-config >../mock.cfg)`
- `mock -r ./mock.cfg --chain sope/sope*.src.rpm sogo/sogo-*.src.rpm --localrepo results`

To run this in a container, install

- `fedpkg`
- `tito`

and run the container with `--privileged` to allow nested containers.

To use `tito` to commit changes, you'll have to set your git user configuration in the container:

```sh
git config --global user.name "Clemens Lang"
git config --global user.email "cl@clang.name"
```

I typically do tito commits using the following command once I have all changes I want to commit staged:

```sh
/usr/bin/tito tag --keep-version --no-auto-changelog
```
