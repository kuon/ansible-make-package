
# THIS REPOSITORY HAS MOVED

New URL: https://git.goyman.com/kuon/ansible-make-package

Why I moved everything out of GitHub:

https://github.com/kuon/WhyILeftGithub/blob/main/README.md

----

Make Package
============

This role install a package from a tarball or a git repository.

Requirements
------------

none

Role Variables
--------------

- `url` - URL of a tarball containing the program you want to install
- `git_url` - Alternative of `url`, full URL to a git repository
- `provides` - The full path of command name of the installed program, used to avoid reinstalling if installed
- `build` - A serie of command used to build the software
- `required_packages` - A serie of yum packages installed before building

Dependencies
------------

none

Example Playbook
----------------


    - hosts: servers
      roles:
      - role: make-package
        url: 'http://www.tortall.net/projects/yasm/releases/yasm-1.3.0.tar.gz'
        provides: yasm
        required_packages:
        - bash
        build:
        - ./configure
        - make
        - make install}

License
-------

MIT

