# ans_role_config_ncmpcpp

Install and configure the ncmpcpp NCurses Music Player Client.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_ncmpcpp.svg?label=release)](https://github.com/digimokan/ans_role_config_ncmpcpp/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Requirements](#requirements)
* [Supported Operating Systems](#supported-operating-systems)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Contributing](#contributing)

## Purpose

* Install [ncmpcpp](https://rybczak.net/ncmpcpp/).
* Configure ncmpcpp.

## Requirements

* A running [MPD](https://www.musicpd.org/) music server.

## Supported Operating Systems

* Ubuntu
* Arch Linux
* FreeBSD

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

   ```yaml
   # requirements.yml
   - src: https://github.com/digimokan/ans_role_config_ncmpcpp
   ```

2. From the project root directory, install/download the role:

   ```shell
   $ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
   ```

   * _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role like any local role, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Install and configure the ncmpcpp NCurses Music Player Client"
         ansible.builtin.include_role:
           name: ans_role_config_ncmpcpp
           public: true
         vars:
           ncmpcpp_user_name: "user2"
           ncmpcpp_music_dir: "/home/user2/Music"
   ```

## Role Options

See the role `defaults` files for main role vars listings:

  * [defaults](../defaults/main/)

Define these _required_ vars for the role:

  * `ncmpcpp_user_name`: user name of main ncmpcpp user
  * `ncmpcpp_music_dir`: dir where user's music tracks are stored

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_ncmpcpp/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

