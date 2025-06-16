# Middle East Flight Tracker Logger

This script logs real-time aircraft data over the Middle East region using the OpenSky Network API. It fetches flight states every 60 seconds and appends them to a CSV log file.

## Features

- Tracks flights within the Middle East bounding box.
- Fetches data from the OpenSky API.
- Parses and logs relevant flight metadata (position, speed, altitude, etc.).
- Saves results to a continuously growing `flight_log.csv` file.
- Strips and normalizes callsign data.
- Runs continuously in a timed loop.

## Requirements

Install dependencies using:

## How It Works

1. **Bounding Box Definition**  
   Focuses on aircraft within:
   - Latitude: 10.0° to 40.0°
   - Longitude: 25.0° to 60.0°

2. **API Call**  
   Sends a request to `https://opensky-network.org/api/states/all` with the bounding box parameters.

3. **Data Cleaning & Formatting**  
   - Removes entries with missing coordinates or time.
   - Formats the Unix timestamp to human-readable format.
   - Strips trailing whitespace from callsigns.

4. **CSV Logging**  
   Appends new data to `flight_log.csv` without headers (after the first run).

5. **Looping Mechanism**  
   Runs every 60 seconds (can be changed in the code). Each iteration prints a counter to the console.

## Usage

Run the script using:

It will begin fetching and logging data every 60 seconds indefinitely.
## Notes

- The OpenSky API has rate limits. For continuous usage, consider creating an OpenSky account and using authentication.
- The script is set to run forever. Use `Ctrl + C` to manually stop it.

## License

This project is open-source and free to use under the MIT License.

