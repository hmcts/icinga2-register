# icinga2-register

A role for hosts to register themselves and their services with a centralised 
icinga2 cluster. The host registration is fairly automatic with no extra YAML
needed, but services need to be set explicitly, by env or group vars in ansible.

This role can be included at deployment time to a host, and read their YAML
service config from icinga2_services[], to set up the service monitoring on
the cluster.

This code started with JJ at devops/icinga2hosts-playbook and went via
https://git.reform.hmcts.net/devops/ansible-oneshots/tree/kev-adding-services-etc/icinga2-test

... and now it's here, being structured for real-world use.

**MOLECULE TESTS**

In order for these to work you'll need to pass in the relevant parameters for
a live icinga2 instance with a working API in order for it to connect to them
and submit tests.

It might be possible to get existing docker images to work as the icinga2 server
to run the tests against, but they persist in generating random passwords for
the icinga2 API admin user which could not be circumvented in short order to
allow it to work.

Work is suspended on this project for now, so I'm leaving this with no 
Jenkinfile_tactical or otherwise to invoke the tests at PR time in order to
avoid blockers.

