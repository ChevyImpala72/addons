# Home Assistant Add-on: Energy Monitoring

## Installation

Follow these steps to get the add-on installed on your system:

1. Navigate to your Home Assistant instance.
2. Go to **Settings** > **Add-ons** > **Add-on Store**.
3. Find the "Energy Monitoring" add-on and click it.
4. Click on the **INSTALL** button.

## Configuration

**Note**: _Remember to restart the add-on when the configuration is changed._

Example add-on configuration:

```yaml
log_level: info
update_interval: 30
currency: "$"
energy_price: 0.12
show_solar: true
show_battery: true
show_grid: true
dark_mode: auto
```

### Option: `log_level`

The `log_level` option controls the level of log output by the add-on and can
be changed to be more or less verbose, which might be useful when you are
dealing with an unknown issue. Possible values are:

- `trace`: Show every detail, like all called internal functions.
- `debug`: Shows detailed debug information.
- `info`: Normal (usually) interesting events.
- `notice`: Normal but significant events.
- `warning`: Exceptional occurrences that are not errors.
- `error`: Runtime errors that do not require immediate action.
- `fatal`: Something went terribly wrong. Add-on becomes unusable.

Please note that each level automatically includes log messages from a
more severe level, e.g., `debug` also shows `info` messages. By default,
the `log_level` is set to `info`, which is the recommended setting unless
you are troubleshooting.

### Option: `update_interval`

The interval in seconds at which the dashboard refreshes energy data.
Valid range is 5 to 300 seconds. Default is 30 seconds.

### Option: `currency`

The currency symbol to display alongside cost estimates. Default is `$`.

### Option: `energy_price`

Your energy price per kWh. This is used to calculate cost estimates.
Default is `0.12`.

### Option: `show_solar`

Whether to show the solar panel section in the dashboard.
Set to `false` if you don't have solar panels. Default is `true`.

### Option: `show_battery`

Whether to show the battery section in the dashboard.
Set to `false` if you don't have battery storage. Default is `true`.

### Option: `show_grid`

Whether to show the grid section in the dashboard.
Set to `false` if you want to hide grid information. Default is `true`.

### Option: `dark_mode`

Controls the theme of the dashboard. Possible values are:

- `auto`: Automatically switch between light and dark based on system preference.
- `light`: Always use light theme.
- `dark`: Always use dark theme.

Default is `auto`.

## Dashboard Features

### Real-time Energy Flow

The dashboard displays a visual representation of energy flowing between:
- **Solar**: Current solar panel production
- **Home**: Current home consumption
- **Grid**: Current grid import/export
- **Battery**: Current battery state and charging status

### Statistics Cards

Quick overview cards showing:
- Today's total consumption
- Solar production
- Estimated cost
- Self-sufficiency percentage

### Energy History Chart

Interactive chart showing energy usage over time with options to view:
- Daily (24 hours)
- Weekly (7 days)
- Monthly (30 days)

### Detailed Breakdowns

Expandable sections with detailed information for:
- Solar (current output, peak, total, efficiency)
- Grid (import, export, net, cost)
- Battery (state of charge, power flow, charged/discharged today)

## Support

Got questions or need help? Please check the [Home Assistant Community Forum][forum]
or open an issue on [GitHub][issues].

[forum]: https://community.home-assistant.io
[issues]: https://github.com/home-assistant/addons/issues
