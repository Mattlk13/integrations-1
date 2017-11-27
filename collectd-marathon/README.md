# ![](https://github.com/signalfx/integrations/blob/master/collectd-marathon/img/integrations_marathon.png) Marathon

Metadata associated with the Marathon plugin for collectd can be found [here](https://github.com/signalfx/integrations/tree/release/collectd-marathon).  The relevant code for the plugin can be found [here](https://github.com/signalfx/collectd-marathon).

- [Description](#description)
- [Requirements and Dependencies](#requirements-and-dependencies)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Metrics](#metrics)
- [License](#license)

### DESCRIPTION

This is the SignalFx Marathon plugin. Follow these instructions to install the Marathon plugin for collectd.

The [collectd-marathon](https://github.com/signalfx/collectd-marathon) plugin collects metrics about Marathon applications and tasks.

#### Features
##### Built-in dashboards

- **Marathon**: Overview of Marathon environment.

  [<img src='./img/dashboard_marathon_overview.png' width=200px>](./img/dashboard_marathon_overview.png)

- **Marathon Application**: Focus on Marathon Applications.

  [<img src='./img/dashboard_marathon_application.png' width=200px>](./img/dashboard_marathon_application.png)

- **Marathon Resources**: Focus on a Marathon Resource Allocation.

  [<img src='./img/dashboard_marathon_resources.png' width=200px>](./img/dashboard_marathon_resources.png)

- **Marathon Task**: Focus on a Marathon Task.

  [<img src='./img/dashboard_marathon_task.png' width=200px>](./img/dashboard_marathon_task.png)

### REQUIREMENTS AND DEPENDENCIES

#### Version information

| Software | Version      |
|----------|--------------|
| collectd | 5.0 or later |
| Python   | 2.6 or later |
| Marathon | 1.1.1 or later |
| Python plugin for collectd | (included with [SignalFx collectd agent](https://github.com/signalfx/integrations/tree/master/collectd)[](sfx_link:sfxcollectd)) |

### INSTALLATION

1.  Download the [collectd-marathon](https://github.com/signalfx/collectd-marathon) Python module onto a host that has access to the Marathon API.

2.  Run the following command to install the module’s dependencies using `pip`, replacing the example path with the download location of the `collectd-marathon` module:

        sudo pip install -r /path/to/collectd-marathon/requirements.txt

3.  Download SignalFx’s [sample configuration file](https://github.com/signalfx/integrations/blob/master/collectd-marathon/20-collectd-marathon.conf) for this plugin to `/etc/collectd/managed_config`.

4.  Modify the configuration file to provide values that make sense for your environment, as described in [Configuration](#configuration) below.

5.  Restart collectd.

### CONFIGURATION
Using the sample configuration file [20-collectd-marathon.conf](https://github.com/signalfx/integrations/blob/master/collectd-marathon/20-collectd-marathon.conf) as a guide, provide values for the configuration options listed below that make sense for your environment.

| configuration option | definition | default value |
| ---------------------|------------|---------------|
| ModulePath | Path on disk where collectd can find this module. | `"/usr/share/collectd/collectd-marathon"` |
| Import | Path to the name of the pythom module with out the .py extension | `marathon` |
| LogTraces | Logs traces from the plugin's execution | `true` |
| verbose | Turns on verbose log statements | `False` |
| host | A python list of `["<scheme>", "<host>", "<port>", "username", "password", "<is_dcos>"]`. `scheme` is either `http` or `https`. The `username` and `password` are only required for Basic Authentication with the Marathon API. `is_dcos` is a string that takes "True" or "False". Set to "True" if operating DC/OS in strict mode |  no default |

**Note**: Metrics from the `/metrics` endpoint are not available while operating in DC/OS strict mode.

### USAGE
All metrics reported by the Marathon collectd plugin will contain the following dimensions:

- `host` will contain the hostname (as known by collectd) of the machine reporting the metrics.
- `plugin` is always set to `marathon`.
- `plugin_instance` will always be `marathon` concated with `.` and the Mesos agent id. Ex. `marathon.<mesos agent id>`.

Sample of built-in dashboard in SignalFx:

![](././img/dashboard_marathon_overview.png)

### METRICS

For documentation of the metrics and dimensions emitted by this plugin, [click here](./docs).

### LICENSE

See [LICENSE](./LICENSE)
