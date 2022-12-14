# y-cruncher-codespaces
Effortlessly deploy y-cruncher on GitHub Codespaces. Simply deploy a Codespace with this repository as the base and GitHub will automagically fetch the binaries in order to run y-cruncher.

## Motive
Acquiring a desktop environment on Codespaces is not the easiest thing to do. The issue is that y-cruncher cannot be installed through a package manager, so the only way to get command-line binaries is by using a utility like `wget`. The Linux download comes in a tarball so you will need to extract in order for everything to work:

```bash
wget http://www.numberworld.org/y-cruncher/y-cruncher%20v0.7.10.9513-static.tar.xz
tar -xzfv "y-cruncher v0.7.10.9513-static.tar.xz"
cd "y-cruncher v0.7.10.9513-static.tar.xz"
./y-cruncher
```

Even then, attempts with `wget` often fail because of domain name resolution errors. This repository eliminates all the stress of setting up y-cruncher in Codespaces. Simply deploy a Codespaces machine and clone this repository, then run the y-cruncher binary straight from the source.

## Starting y-cruncher
In the root directory of this repository lives the y-cruncher entrypoint executable. Codespaces by default uses non-executable permissions for all important files. Therfore, you must run the following commands in the current working directory to get y-cruncher going:

```sh
chmod +x y-cruncher
chmod -R +x Binaries
```

Now, you should be able to run y-cruncher normally as if you have downloaded fresh off the internet.
