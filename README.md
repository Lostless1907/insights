# Jammu AQI Intelligence System

Dual sensor air quality analysis, calibration, and prediction

## What this is

This project studies air quality in Jammu using two different data sources:

* AirGradient sensor for local, high resolution measurements
* AQI.in station for city level reference

The goal is to go beyond raw numbers and actually understand what is happening, why it is happening, and whether it can be predicted.

## What I am trying to do

* Compare two independent AQI measurement systems and see how they differ
* Find consistent patterns in pollution across time
* Understand how weather affects AQI
* Figure out when my local area behaves differently from the city
* Build a basic system that can predict AQI in the near future

## Where the data comes from

### AirGradient

* PM2.5
* PM10
* CO2
* Temperature
* Humidity
* High frequency local readings

### AQI.in

* AQI index
* PM2.5 and PM10
* City level measurements

### Weather data

* Wind speed
* Wind direction
* Temperature
* Humidity
* Rain

## Making the data usable

* Align all timestamps to the same timezone
* Convert everything into consistent intervals (usually hourly)
* Handle missing values and remove obvious outliers
* Make sure units match across sources

If this step is wrong, everything after this is useless.

## What I look for in the data

### How different are the sensors

I compare AirGradient with AQI.in over time.

Things I check:

* Is one always higher or lower
* Does the gap change over time
* Does weather affect the difference

This is basically testing how trustworthy each system is.

### When does pollution actually happen

I average AQI across hours of the day.

Questions:

* When are the peaks
* Are they consistent
* How strong are daily cycles

You usually see spikes in the morning and evening.

### What weather is doing

I check how AQI changes with:

* Wind speed
* Humidity
* Temperature
* Rain

This is where patterns start to make sense instead of just existing.

### Is my area different from the city

I compare my sensor with AQI.in directly.

I want to know:

* When my area is worse
* When it is better
* Whether there are local sources affecting it

This is important because city level AQI hides local variation.

### Does pollution move over time

I shift one dataset forward and backward in time and check correlation.

If one consistently comes before the other, it suggests pollution is spreading rather than appearing randomly.

### Can this be predicted

I build simple models using:

* Past AQI values
* Weather data

Start simple and see what actually works.

## What this produces

* Clean and aligned dataset
* Clear comparison between two sensors
* Daily AQI patterns
* Measurable effect of weather
* Evidence of local differences
* A working prediction model

## What I want to add later

* More sensors for better coverage
* Better prediction models
* A live dashboard
* Automatic explanations for AQI spikes
* A system people can actually use

## Tools

* Python
* Pandas and NumPy
* Matplotlib or Plotly
* scikit-learn
* Streamlit

## Final idea

AQI is not random. It follows patterns driven by weather and human activity.

The point of this project is to take a small amount of data and extract as much structure and meaning from it as possible.
