# Wasp in the Box Sensor Configuration

This document outlines the sensor requirements and configuration for the Wasp in the Box lighting automation system.

## Required Sensors

### 1. Door Sensor

- **Type**: Binary Sensor
- **Device Class**: door
- **States**:
  - `on` = Door Open
  - `off` = Door Closed
- **Requirements**:
  - Must reliably detect door state changes
  - Should respond quickly to state changes
- **Recommended Sensors**:
  - Reed switch sensor
  - Door/window contact sensor
  - ZigBee/Z-Wave door sensor

### 2. Presence Sensors

- **Type**: Binary Sensor
- **Device Class**: motion or occupancy
- **States**:
  - `on` = Presence Detected
  - `off` = No Presence
- **Requirements**:
  - Can use multiple sensors for better coverage
  - Should have appropriate detection range for space
  - Must handle false positives gracefully
- **Recommended Sensors**:
  - PIR motion sensors
  - mmWave presence sensors
  - Camera-based presence detection

## Helper Entities

### Wasp Mode Toggle

- **Type**: Input Boolean
- **Purpose**: Tracks whether wasp mode is active
- **States**:
  - `on` = Wasp Mode Active
  - `off` = Wasp Mode Inactive

## Timing Configuration

Two critical timing parameters affect sensor behavior:

1. **Brief Light On Duration**

   - Default: 30 seconds
   - Range: 1-600 seconds
   - Purpose: Duration lights stay on with open door

2. **No Presence Off Delay**
   - Default: 300 seconds (5 minutes)
   - Range: 10-3600 seconds
   - Purpose: Grace period before turning off lights after last presence detection

## Sensor Placement Guidelines

1. **Door Sensor**

   - Mount on door frame and door
   - Ensure proper alignment
   - Test reliable activation range

2. **Presence Sensors**
   - Position for maximum coverage
   - Avoid false triggers from:
     - HVAC systems
     - Windows (direct sunlight)
     - Moving objects
   - Consider overlapping coverage for reliability

## Integration Testing

1. Test door sensor state changes
2. Verify presence sensor coverage
3. Validate timing configurations
4. Check wasp mode activation/deactivation
5. Confirm proper light control behavior

## Troubleshooting

Common sensor issues and solutions:

1. **Door Sensor**

   - Check alignment
   - Verify battery level
   - Test signal strength

2. **Presence Sensors**
   - Adjust sensitivity
   - Reposition if false triggers occur
   - Check detection zones
