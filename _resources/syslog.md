---
title: "Syslog"
---

## Resource Creation

You can forward your logs to syslog using the `convox resources create` command:

    $ convox resources create syslog --url=tcp+tls://logs1.papertrailapp.com:12345
    Creating syslog-3785 (syslog)... CREATING

This will create a syslog forwarder. Creation will take a few moments. To check the status use `convox resources info`.

### Additional Options

<table>
  <tr><th>Option</th><th>Description</th></tr>
  <tr><td><code>--name=<b><i>&lt;name&gt;</i></b></code></td><td>The name of the resource to create</td></tr>
  <tr><td><code>--private</code></td><td>Create in private subnets</td></tr>
</table>

## Resource Information

To see relevant info about the forwarder, use the `convox resources info` command:

    $ convox resources info syslog-3785
    Name    syslog-3785
    Status  running
    Exports
      URL: tcp+tls://logs1.papertrailapp.com:12345

## Resource Linking

To forward logs from an application to a syslog forwarder use `convox resources link`:

    $ convox resources link syslog-3785 --app example-app
    Linked syslog-3786 to example-app

## Resource Deletion

To delete the syslog forwarder, use the `convox resources delete` command:

    $ convox resources delete syslog-3785
    Deleting syslog-3785... DELETING
