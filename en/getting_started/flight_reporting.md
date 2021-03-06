# Flight Reporting

PX4 logs detailed aircraft performance data once the system has been armed until it is disarmed. These flight logs can also be used to analyze performance issues.

> **Tip** Keeping flight logs is a legal requirement in some jurisdictions. 

## Downloading Logs from the Flight Controller

Logs can be downloaded using [QGroundControl](http://qgroundcontrol.com/) (v3.2 or later): **[Analyze View > Log Download](https://docs.qgroundcontrol.com/en/analyze_view/log_download.html)**.

![Flight Log Download](../../assets/qgc/analyze/log_download.jpg)


## Sharing the Log Files for Review by PX4 Developers

Upload the log files to [Flight Review](http://logs.px4.io) (http://logs.px4.io). 
The log file link can then be shared for review in [discussion forums](../README.md#support) or a [Github issue](../README.md#reporting-bugs--issues).

> **Tip** The topic [Flight Log Analysis](https://dev.px4.io/en/log/flight_log_analysis.html) (PX4 Developer Guide) contains basic information about log file analysis (and alternative analysis tools).


## Additional Configuration

The logging system is configured by default to collect sensible logs for use with [Flight Review](http://logs.px4.io).

Logging may further be configured using the [SD Logging](../advanced_config/parameter_reference.md#sd-logging) parameters.
The parameters you are most likely to change are listed below.

Parameter | Description
--- | ---
[SDLOG_MODE](../advanced_config/parameter_reference.md#SDLOG_MODE) | Logging Mode defines when logging starts and stops.<br />- `0`: log when armed until disarm (default)<br />- `1`: log from boot until disarm<br />- `2`: log from boot until shutdown.
[SDLOG_PROFILE](../advanced_config/parameter_reference.md#SDLOG_PROFILE) | Logging profile. Use this to enable less common logging/analysis (e.g. for EKF2 replay, high rate logging for PID & filter tuning, thermal temperature calibration).
[SDLOG_MISSION](../advanced_config/parameter_reference.md#SDLOG_MISSION) | Create very small additional "Mission Log". 
  This log can *not* be used with *Flight Review*, but is useful when you need a small log for geotagging or regulatory compliance.

Developers can further configure what information is logged via the [logger](https://dev.px4.io/en/middleware/modules_system.html#logger) module
(you would use this, for example, if you want to log your own topics).
For more information see: [Logging](https://dev.px4.io/en/log/logging.html) (PX4 Developer Guide).

