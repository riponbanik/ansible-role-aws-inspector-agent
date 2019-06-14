# Ansible Role: AWS Inspector

[![Build Status](https://travis-ci.org/riponbanik/ansible-role-aws-inspector-agent.svg?branch=master)](https://travis-ci.org/riponbanik/ansible-role-aws-inspector-agent)

Installs [AWS Inspector](https://aws.amazon.com/inspector/) (awsagent) on both Windows and Linux(RedHat/CentOS or Debian/Ubuntu).

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    aws_inspector_url: "https://inspector-agent.amazonaws.com/linux/latest/install"
    aws_inspector_installer_dest: /tmp/aws_inspector_agent_installer

URL from which inspector installer will be downloaded, and temporary directory where installer will be stored.

    awsagent_state: started
    awsagent_enabled: true

Control the `awsagent` service; by default, for Amazon Inspector to work correctly, you must have `awsagent` running on any server you want inspected.

There is also a handler, `restart awsagent`, which can be used to restart the agent.

    aws_inspector_role_test_mode: false

Set this to `true` if testing or using this role outside of an EC2 instance (e.g. if testing in CI or building a server in a different cloud environment).

    use_proxy: true
    proxy_host: proxy.example.com
    proxy_port: 80  

Using Proxy - Set the above variable to configure it to connect AWS Inspector Endpoint via proxy
  

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - { role: riponbanik.aws-inspector-agent }

## License

MIT / BSD

## Author Information

This role was created in 2019 by [Ripon Banik ](https://www.linkedin.com/in/ripon-banik-79956b23/). Inspired from https://github.com/geerlingguy/ansible-role-aws-inspector.
