---
title: Light Temperature Cards
description:
  How to use light temperature slider cards on your EspControl panel to control the colour temperature of a Home Assistant light entity.
---

# Light Temperature

A light temperature card lets you control the colour temperature of a Home Assistant light entity by dragging a vertical fill bar. The bottom of the slider is the coolest (lowest kelvin) setting and the top is the warmest (highest kelvin).

## Setting Up a Light Temperature Card

1. Select a card and change its type to **Light Temperature**.
2. Enter an **Entity ID** — the Home Assistant light entity you want to control (for example, `light.living_room`).
3. Set **Min Color Temp (K)** and **Max Color Temp (K)** to match the range supported by your light. The defaults (2000 K–6500 K) cover most tunable white bulbs.
4. Choose an **Icon** (optional). If left as Auto, the domain default icon is used.
5. Set a **Label** (optional) — shown at the bottom of the card. If left blank, the entity's friendly name from Home Assistant is used.

## Options

### Tap to toggle light

When enabled, tapping the card without dragging will toggle the light on or off. When disabled, tapping has no effect — only dragging the slider sends a command.

### Color fill by temperature

When enabled, the fill bar changes colour to reflect the current colour temperature rather than using your configured accent colour. The fill transitions from a warm amber at the low end to a cool blue-white at the high end, giving you a visual indication of the current setting at a glance.

## How It Works on the Panel

- **Drag** the fill bar to set the colour temperature. Releasing the slider sends the new value to Home Assistant using `light.turn_on` with `color_temp_kelvin`.
- When the light's colour temperature changes externally (from Home Assistant or another control), the fill bar updates automatically.
- The slider covers only the kelvin range you configured — values outside that range are clamped.
