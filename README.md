# ancypwn
Ancypwn is a small project to make pwn environment easily managed.

It uses docker as a seperate environment for pwn development, and provided a script to manage this docker image(container).

Currently, this can only run under linux environment. So the goal of this project for now is to provide a seperate environment for linux user who
wants to do finish some CTF pwn challenges, especially who doesn't use ubuntu but other distributions which is not used widely as pwn server.

This docker image provide:
* gef
* pwntools
* keystone assmebler
* capstone disassembler
* glibc source and debug version glibc(so we can debug libc with source)
* Ropper
* ROPGadgets
* one_gadget

Nothing else for now, and it is sufficient most of the time. If you have some suggestion of what is needed or how to make this image smaller, 
it is welcome to comment an issue.

# Installation
1. Install docker, we recommend you to let your distribution to do so.
2. Since the image is too huge to upload, we provide you a `Dockerfile`, you can build an image yourself. And, please do that by using given `build.sh`, run `build.sh` under linux distribution where `docker` is provided should be sufficient. If not? Please give me an issue and describe what's wrong.
3. Run `python setup.py install`, or maybe you need `sudo`. Pip version is also provided and recommended `pip install ancypwn`
4. Everything should be good by now. If you got permission problems, try `sudo`

# Usage

```
usage: ancypwn [-h] {run,attach,end} ...

Anciety's pwn environment

positional arguments:
  {run,attach,end}  Actions you can take
    run             run a pwn thread
    attach          attach to running thread
    end             end a running thread

optional arguments:
  -h, --help        show this help message and exit

```