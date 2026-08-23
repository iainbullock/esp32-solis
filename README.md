# ESP32 Solis

An ESPHome-based project for integrating a Solis inverter with a household energy model.

The project is being developed around a real home-energy installation and is currently experimental. Interfaces, assumptions, and configuration details may change while the model is validated against collected data.

## Goals

- Forecast household load and PV generation.
- Model battery state of charge over the forecast horizon.
- Account for grid import, grid export, inverter behaviour, and scheduled charging.
- Support deliberate export events and other unusual operating periods.
- Provide reusable ESPHome/C++ components for similar Solis installations.

## Project status

Early development. The energy model is being validated using measured data before this repository is considered a stable release.

## Repository layout

- `components/energy_model/` — reusable ESPHome energy-model component.
- `esphome/` — device configuration examples and integration notes.
- `examples/` — examples for adapting the project.
- `docs/` — design notes, assumptions, and data-model documentation.

## Important notes

This project is not currently a drop-in configuration. Your inverter, battery, tariff, sensors, time zone, and ESPHome version may require different settings.

Do not commit:

- Wi-Fi passwords or API keys.
- Solis, Axle, or other service credentials.
- Inverter serial numbers or device identifiers.
- Raw household energy data containing personal or location information.
- Local tariff or account details unless deliberately anonymised.

Use ESPHome's `secrets.yaml` mechanism for credentials and keep personal configuration separate from reusable examples.

## Planned documentation

- Hardware and wiring requirements.
- Required Solis and ESPHome entities.
- Configuration parameters.
- Energy-flow definitions and units.
- Forecast and battery-model assumptions.
- Data collection and validation methodology.

## License

The software is available under the [PolyForm Noncommercial License 1.0.0](LICENSE). Noncommercial use is permitted under its terms. Commercial use requires separate permission from the copyright holder.
