# Smart Device Management System

A Python Object-Oriented Programming (OOP) mini project simulating a smart home
device management system. It demonstrates core OOP concepts: classes, objects,
constructors, inheritance, encapsulation, `@property` getters/setters, and `super()`.

## Project Overview

A smart home technology company needs software to manage its smart devices.
Every device shares common information (name, device ID, power status), but
each device type also has its own unique behavior. Sensitive data (device ID,
power status) is encapsulated and can only be changed through controlled methods.

## Class Structure

- **SmartDevice** (parent class)
  - Private attributes: `__device_id`, `__power_status`
  - Public attribute: `name`
  - Methods: `turn_on()`, `turn_off()`, `display_info()`
  - Access to private attributes controlled via `@property`

- **SecurityCamera** (inherits from `SmartDevice`)
  - Additional attribute: `recording_status`
  - Methods: `start_recording()`, `stop_recording()`

- **SmartLight** (inherits from `SmartDevice`)
  - Additional attribute: `brightness` (validated between 0–100)
  - Methods: `increase_brightness()`, `decrease_brightness()`

- **TemperatureSensor** (inherits from `SmartDevice`)
  - Additional attribute: `temperature`
  - Method: `read_temperature()`

## Encapsulation & Validation

- `device_id` cannot be empty (checked in the constructor).
- `power_status` cannot be set directly with a non-boolean value.
- `brightness` must stay between 0 and 100; invalid values are rejected
  with an error message instead of crashing the program.
