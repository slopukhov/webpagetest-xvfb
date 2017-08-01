# webpagetest-xvfb

Based off [dominykas/webpagetest-xvfb](https://github.com/dominykas/webpagetest-xvfb) repository.

## About

For local installation [WebPagetest Private Instance](https://github.com/WPO-Foundation/webpagetest), with a local Chrome(chromium) agent driven by the [node.js agent](https://sites.google.com/a/webpagetest.org/docs/private-instances/node-js-agent/setup) and [Xvfb](http://en.wikipedia.org/wiki/Xvfb).

WebPagetest server and agent are configured to run all on one system -
CentOS
(with the web server and tests machine all running on the same VM).

The `webpagetest-agent` Ansible role will:

- Install Chrome(chromium) and Xvfb
- Setup appropriate webpagetest's locations.ini file, with a "Local"
  location
- Setup init.d script for Xvfb and the Chrome agent - `tail -f
  /opt/webpagetest/agent/js/agent.log` to see the agent logs

## Requirements

* [Vagrant](http://vagrantup.com/)
* [VirtualBox](http://virtualbox.org)
* [Ansible](http://ansible.com/) for provisioning

## Usage

### Clone repository

```sh
$ git clone https://github.com/slopukhov/webpagetest-xvfb
```

### Boot vagrant

```sh
$ vagrant up
```

### Browse `http://192.168.33.33:8080`

and launch a test

## License

MIT
