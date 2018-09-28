# ![](https://github.com/signalfx/integrations/blob/master/collectd/img/integrations_collectd.png) Interface

Metadata associated with the Interface plugin for collectd can be found [here](https://github.com/signalfx/integrations/tree/release/collectd-interface). The relevant code for the plugin can be found [here](https://github.com/signalfx/collectd/blob/master/src/interface.c).

- [Description](#description)
- [Requirements and Dependencies](#requirements-and-dependencies)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Metrics](#metrics)
- [License](#license)

### DESCRIPTION

From [collectd wiki](https://collectd.org/wiki/index.php/Plugin:Interface):

The Interface plugin collects information about the traffic (octets per second), packets per second and errors of interfaces (of course number of errors during one second). If you're not interested in all interfaces but want to exclude some, or only collect information of some selected interfaces, you can select the “interesting” interfaces using the plugin's configuration.

### REQUIREMENTS AND DEPENDENCIES

This plugin requires:

| Software  | Version        |
|-----------|----------------|
| collectd  | 1.0+ |

### INSTALLATION

**If you are using the new Smart Agent, see the docs for [the collectd/interface
monitor](https://github.com/signalfx/signalfx-agent/tree/master/docs/monitors/collectd-interface.md)
for more information.  The configuration documentation below may be helpful as
well, but consult the Smart Agent repo's docs for the exact schema.**


Installation and initial configuration options are available as part of the [SignalFx collectd agent](https://github.com/signalfx/integrations/tree/master/collectd).


### CONFIGURATION

#### Optional configuration

The following configuration options are *optional*. You may specify them in the configuration file in order to override default values provided by the plugin.

| configuration option | definition | default value |
| ---------------------|------------|---------------|
| Interface | Include specific Interface(s) | "lo" "sit0" |
| IgnoreSelected  | Ignore the designation of specific Disks | true |

### USAGE

The primary use of this plugin is to track the I/O of system interfaces. This is not only valuable data to understand the workloads on specific systems but can be combined with other system and application metrics to identify issues related to network and data I/O traffic.

The [SignalFx collectd plugin](https://github.com/signalfx/integrations/tree/release/signalfx-metadata) computes aggregated utilization metrics based on the output of this plugin you can learn more by looking at the [metrics for the plugin](https://github.com/signalfx/integrations/tree/release/signalfx-metadata/docs).

### METRICS

For documentation of the metrics and dimensions emitted by this plugin, [click here](./docs).

### LICENSE

License for this plugin can be found [in the header of the plugin](https://github.com/signalfx/collectd/blob/master/src/interface.c)
