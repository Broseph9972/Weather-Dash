# TRMNL Weather Dashboard

A starter plugin for the [TRMNL](https://usetrmnl.com/) e-ink display. The
plugin is built with TRMNL's Liquid templates and framework classes, and can
be previewed locally with `trmnlp`.

## Project layout

```text
src/
  full.liquid           Full-screen layout
  half_horizontal.liquid
  half_vertical.liquid
  quadrant.liquid
  settings.yml          Plugin settings and polling configuration
.trmnlp.yml             Local preview data and watch configuration
```

`dashboard.liquid` is the shared source of truth for the initial dashboard.
The layout files are intentionally small responsive entry points that can be
expanded as the design develops.

## Local preview

Install the [TRMNL Preview CLI](https://github.com/usetrmnl/trmnlp), then run
these commands from the repository root:

```sh
trmnlp serve
```

Open <http://localhost:4567> to view the dashboard. Edit files under `src/`
and refresh the browser; `.trmnlp.yml` enables file watching.

## Data contract

The starter renders the Open-Meteo response fields configured in
`src/settings.yml`:

- `current_weather.temperature`
- `current_weather.windspeed`
- `current_weather.weathercode`
- `daily.time`
- `daily.temperature_2m_max`
- `daily.temperature_2m_min`

Replace the sample values in `.trmnlp.yml` as the template evolves. The
polling URL uses the configured latitude, longitude, and unit settings.

## Next steps

1. Install `trmnlp` and validate the template with `trmnlp lint`.
2. Replace the sample data with the fields you want to display.
3. Create a Private Plugin in TRMNL and copy the settings and markup into it,
   or use the CLI workflow for publishing a plugin.
