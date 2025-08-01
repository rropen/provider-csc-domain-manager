<p>
    <img alt="Rolls-Royce Logo" width="100" src="https://raw.githubusercontent.com/rropen/MEC/main/src/frontend/public/logo4.png">
    <br>
    <h3>Crossplane Provider for CSC Domain Manager</h3>
</p>
<p>
<a href="https://ghdocs.rollsroyce-sf.com"><img src="https://img.shields.io/badge/Rolls--Royce-Software%20Factory-10069f" alt="sf badge" /></a>
</p>

---

<p>
  <a href="http://commitizen.github.io/cz-cli/"><img src="https://img.shields.io/badge/commitizen-friendly-brightgreen?style=flat" alt="commitizen badge" /></a>
  <a href="https://go.dev/"><img src="https://img.shields.io/badge/golang-%2300ADD8.svg?style=flat&logo=go&logoColor=white" /></a>
</p>


`provider-csc-domain-manager` is a [Crossplane](https://crossplane.io/) provider that
is built using [Upjet](https://github.com/crossplane/upjet) code
generation tools and exposes XRM-conformant managed resources for the
CSC Domain Manager API.

## Getting Started

Install the provider by using the following command after changing the image tag
to the [latest release](https://marketplace.upbound.io/providers/rropen/provider-csc-domain-manager):
```
crossplane xpkg install provider xpkg.crossplane.io/rropen/provider-csc-domain-manager:v0.1.0
```

Alternatively, you can use declarative installation:
```
cat <<EOF | kubectl apply -f -
apiVersion: pkg.crossplane.io/v1
kind: Provider
metadata:
  name: provider-csc-domain-manager
spec:
  package: xpkg.crossplane.io/rropen/provider-csc-domain-manager:v0.1.0
EOF
```

Notice that in this example Provider resource is referencing ControllerConfig with debug enabled.

You can see the API reference [here](https://doc.crds.dev/github.com/rropen/provider-csc-domain-manager).

## Developing

Run code-generation pipeline:
```console
go run cmd/generator/main.go "$PWD"
```

Run against a Kubernetes cluster:

```console
make run
```

Build, push, and install:

```console
make all
```

Build binary:

```console
make build
```

## Report a Bug

For filing bugs, suggesting improvements, or requesting new features, please
open an [issue](https://github.com/rropen/provider-csc-domain-manager/issues).
