slackpkgplus
============

Ansible role that bootstraps the installation of [slackpkg+](http://www.slakfinder.org/slackpkg+.html) on a Slackware system.

Requirements
------------

* Slackware
* `slackpkg` installed.
* `become: true`

Default Role Variables
----------------------

| Variable                  | Default | Description                                                              |
|:-------------------------:|:-------:|:-------------------------------------------------------------------------|
|slackpkgplus_major_version | (blank) | The major version of slackpkg+ for the repository URL.                   |
|slackpkgplus_repos         | {}      | A dictionary of slackpkg+ repos: key is name, value is URL.              |

By default, the enabled repositories are all of the repos defined in `slackpkgplus_repos`, however you can also
set `slackpkgplus_enabled_repos` to a _list_ of all the repositories that will be enabled in slackpkg+.

:information_source: If you set `slackpkgplus_enabled_repos`, be sure to add the `slackpkgplus` repository for 
slackpkg+ updates, if desired!  It will not be added automatically.


Role Variables
--------------

The following variables are defined in vars/main.yml:

| Variable             | Default                         | Description                          |
|:--------------------:|:-------------------------------:|:-------------------------------------|
|slackpkgplus_base_url | http://slakfinder.org/slackpkg+ | The base URL for slackpkg+ packages. |


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      become: true
      vars:
        slackpkgplus_repos:
          slackpkgplus: "http://slakfinder.org/slackpkg+/"
        slackpkgplus_enabled_repos:
          - slackpkgplus
      roles:
        - slackpkgplus

License
-------

MIT License

Copyright (c) 2018 Ken Treadway

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
