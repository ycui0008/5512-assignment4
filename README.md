5512-assignment4

Exercise 1 and 3 both requires save data sets in rda format, to differentiate the files saved for different exercises, all rda files in Exercise 3 are named after my_, for example, my_flights.rda.


my_flights.rda
- Description
  On-time data for all flights that departed/arrived ATL in February 2019.
- Format
	Data frame with columns
	
	year, month, day
		Date of departure.

	dep_time, arr_time
		Actual departure and arrival times (format HHMM or HMM), local tz.

	sched_dep_time, sched_arr_time
		Scheduled departure and arrival times (format HHMM or HMM), local tz.

	dep_delay, arr_delay
		Departure and arrival delays, in minutes. Negative times represent early departures/arrivals.

	carrier
		Two letter carrier abbreviation. See airlines to get name.

	flight
		Flight number.

	tailnum
		Plane tail number. See planes for additional metadata.

	origin, dest
		Origin and destination. See airports for additional metadata.

	air_time
		Amount of time spent in the air, in minutes.

	distance
		Distance between airports, in miles.

	hour, minute
		Time of scheduled departure broken into hour and minutes.

	time_hour
		Scheduled date and hour of the flight as a POSIXct date. Along with origin, can be used to join flights data to weather data.
- Source
  RITA, Bureau of transportation statistics, https://www.transtats.bts.gov/DL_SelectFields.asp?Table_ID=236


my_airlines.rda
- Description
  Look up airline names from their carrier codes.
- Format
  	Data frame with columns

	carrier
		Two letter abbreviation.

	name
		Full name.

- Source
  https://www.transtats.bts.gov/DL_SelectFields.asp?Table_ID=236


my_airports.rda
- Description
  Useful metadata about airports.
- Format
	A data frame with columns:

	faa
		FAA airport code.

	name
		Usual name of the aiport.

	lat, lon
		Location of airport.

	alt
		Altitude, in feet.

	tz
		Timezone offset from GMT.

	dst
		Daylight savings time zone. A = Standard US DST: starts on the second Sunday of March, ends on the first Sunday of November. U = unknown. N = no dst.

	tzone
		IANA time zone, as determined by GeoNames webservice.
- Source
  http://openflights.org/data.html, downloaded 2014-06-27


my_planes.rda
- Description
  Plane metadata for all plane tailnumbers found in the FAA aircraft registry. American Airways (AA) and Envoy Air (MQ) report fleet numbers rather than tail numbers so can't be matched.
- Format
	A data frame with columns:

	tailnum
		Tail number.

	year
		Year manufactured.

	type
		Type of plane.

	manufacturer, model
		Manufacturer and model.

	engines, seats
		Number of engines and seats.

	speed
		Average cruising speed in mph.

	engine
		Type of engine.

- Source
  FAA Aircraft registry, http://www.faa.gov/licenses_certificates/aircraft_certification/aircraft_registry/releasable_aircraft_download/

my_weather.rda
- Description
  Hourly meterological data for LGA, JFK and EWR.
- Format
  	A data frame with columns

	origin
		Weather station. Named origin to facilitate merging with flights data.

	year, month, day, hour
		Time of recording.

	temp, dewp
		Temperature and dewpoint in F.

	humid
		Relative humidity in %.

	wind_dir, wind_speed, wind_gust
		Wind direction (in degrees), speed and gust speed (in mph).

	precip
		Precipitation, in inches.

	pressure
		Sea level pressure in millibars.

	visib
		Visibility in miles.

	time_hour
		Date and hour of the recording as a POSIXct date.

- Source
  ASOS download from Iowa Environmental Mesonet, https://mesonet.agron.iastate.edu/request/download.phtml.