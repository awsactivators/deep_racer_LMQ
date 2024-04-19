# DeepRacer Reward Function
### Team Lighting McQueen | Humber College IGS
Ryhan Sunny ||
Sharmi Das ||
Noah Nsimbe ||
Murtuza Salman Mohammed ||
Amaka Genevieve Jane Awa

This repository contains the Python code for a reward function used in AWS DeepRacer competitions. The reward function is designed to guide a DeepRacer vehicle along a predefined track by calculating a score based on the vehicle's heading alignment with the track's waypoints.

## Function Overview

The reward function `reward_function` takes a single parameter `params`, a dictionary containing various pieces of information about the vehicle's current state on the track. The function calculates a reward score that encourages the vehicle to align its heading with the track's direction.

## Key Inputs

- `waypoints`: A list of (x, y) tuples representing the coordinates of the track's waypoints.
- `closest_waypoints`: A tuple containing the indices of the two waypoints closest to the vehicle’s current position (previous and next waypoints).
- `heading`: The vehicle's current heading in degrees, representing its orientation relative to the north.

## Reward Calculation

1. **Baseline Score**: Starts with a default reward of 1.0.
2. **Direction Calculation**:
   - Determines the direction of the track between the two closest waypoints.
   - Converts this direction from radians to degrees.
3. **Direction Difference**:
   - Calculates the absolute difference between the vehicle's heading and the track's direction.
   - Adjusts differences that exceed 180 degrees to measure the shorter arc around the circle.
4. **Penalty**:
   - Penalizes the reward by half if the difference between the vehicle's heading and the track's direction exceeds a threshold of 10 degrees.

## Usage

To use this reward function in your AWS DeepRacer console:
1. Copy the Python code into the reward function editor.
2. Modify the parameters or the function logic as needed based on specific race conditions or desired behaviors.
3. Test the function in simulations to ensure it behaves as expected under various track conditions.

## License

This code is released under the MIT license.

---
