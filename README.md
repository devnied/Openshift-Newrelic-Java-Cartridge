OpenShift New Relic Java Agent cartridge
===================================

An embedded cartridge to enable New Relic Monitoring for Java applications deployed on OpenShift JBoss cartridges.

The cartridge installs the latest release of the New Relic for Java agent, property of New Relic. https://docs.newrelic.com/docs/release-notes/agent-release-notes/java-release-notes
To see detailed information about usage conditions see https://docs.newrelic.com/docs/licenses/licenses

Requirements
------------

- A [New Relic](http://www.newrelic.com/) account.
- OpenShift JBoss AS/EAP/EWS as primary cartridge.


Install
-------

- Install the cartridge from GitHub.

```
  rhc cartridge-add -a <your_app_name> \
    -e OPENSHIFT_NEWRELIC_LICENSE_KEY=<your_new_relic_key> \
    -c https://raw.githubusercontent.com/devnied/Openshift-Newrelic-Java-Cartridge/master/metadata/manifest.yml
  rhc env-set JAVA_OPTS_EXT="-javaagent:${OPENSHIFT_NEWRELIC_DIR}newrelic/newrelic.jar" -a <your_app_name>
```

- Restart your application.

```
  rhc app restart <your_app_name>
```

Remove
------

```
  rhc cartridge-remove newrelic -a <your_app_name>
```
