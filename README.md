# java

To vendor java package into your release, run:

```
$ git clone https://github.com/MirkoNikolai/java-release
$ cd ~/workspace/your-release
$ bosh vendor-package openjre-11 ~/workspace/java-release
```

Included packages:

- openjdk-11
- openjdk-8
- openjre-11
- openjre-8

All packages use the AdoptOpenJDK provided tar.gz files. 

To use `openjdk-*` package for compilation in your packaging script:

```bash
#!/bin/bash -eu
source /var/vcap/packages/openjdk-9/bosh/compile.env
java ...
```

To use `openjre-*` package at runtime in your job scripts:

```bash
#!/bin/bash -eu
source /var/vcap/packages/openjdk-8/bosh/runtime.env
java ...
```

See [jobs/openjdk-8-test](jobs/openjre-8-test) for example.

## Development

To run tests `cd tests/ && BOSH_ENVIRONMENT=vbox ./run.sh`

## TODO

- add custom trust store building to runtime.env
