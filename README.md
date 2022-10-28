1) Build the container:

    docker build -t zenddecoder .

2) Run the container, with the code base as a bind mount, and drop into a shell:

    docker run -v /path/to/your/codebase:/src -it zenddecoder /bin/bash

3) Now it’s possible to deobfuscate your entire code base with one-liners like this:

    for f in $(find /src/ -name '*.php'); do php index.php $f > ${f::-4}".dec.php"; done"
