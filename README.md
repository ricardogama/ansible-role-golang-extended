# ansible-role-golang-extended

A couple of extra features for [ansible-role-golang](https://github.com/fubarhouse/ansible-role-golang)

## Status

[![galaxy](https://img.shields.io/ansible/role/24553.svg?style=for-the-badge)](https://galaxy.ansible.com/ricardogama/golang-extended/) [![license](https://img.shields.io/badge/license-MIT-blue.svg?style=for-the-badge)](https://raw.githubusercontent.com/ricardogama/ansible-role-golang-extended/master/LICENSE)

## Link go binaries

Since `GOPATH` and `GOROOT` are not set by the parent role, it can be handy to create symbolic links for go binaries so you can execute them in any environment.

Below is default directory where the binaries are linked:

```yaml
go_bin_link_dir: /usr/local/bin
```

By default, links for `go`, `gofmt` and `godoc` are created, but you can disable it by overriding the `go_link_bin` variable:

```yaml
go_bin_link_root: false
```

If you only want to link some of the root binaries, override the default list:

```yaml
go_bin_link_root_items:
  - go
  - gofmt
  - godoc
```

You can also create links for the binaries installed with `go_get` by adding the `link` entry, for example:

```yaml
go_get:
  - name: gopm
    url: github.com/gpmgo/gopm
    link: true
  - name: golint
    url: github.com/golang/lint/golint
    link: true
```
