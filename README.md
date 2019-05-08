# ![LOGO](logo.png) Bus Route and Stop Methods **flow**ground Connector

## Description

A generated **flow**ground connector for the Bus Route and Stop Methods API (version 1.0).

Generated from: https://api.apis.guru/v2/specs/wmata.com/bus-route/1.0/swagger.json<br/>
Generated at: 2019-05-07T17:44:59+03:00

## API Description

Bus stop information, route and schedule data, and bus positions.

## Authorization

Supported authorization schemes:
- API Key- API Key
## Actions

### XML - Bus Position

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns bus positions for the given route, with an optional search radius.<br/>
> If no parameters are specified, all bus positions are returned.</p><br/>
> <br/>
> <p>Note that the RouteID parameter accepts only base route names and no<br/>
> variations, i.e.: use 10A instead of 10Av1 or 10Av2.</p><br/>
> <br/>
> <p>Bus positions are refreshed approximately every <span style="text-decoration: line-through">20 to 30</span> 7 to 10 seconds.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>BusPositions</td><br/>
> <br/>
> <td><br/>
> Array containing bus position information (<a href=<br/>
> "#BusPosition">BusPositions</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="BusPosition" name="BusPosition">BusPosition<br/>
> Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DateTime</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) of last position update.<br/>
> Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:23:40).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Deviation</td><br/>
> <br/>
> <td>Deviation, in minutes, from schedule. Positive values indicate<br/>
> that the bus is running late while negative ones are for buses<br/>
> running ahead of schedule.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">DirectionNum</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span> Use the<br/>
> DirectionText for a customer-friendly description of<br/>
> direction.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DirectionText</td><br/>
> <br/>
> <td>General direction of the trip, not the bus itself (e.g.: NORTH,<br/>
> SOUTH, EAST, WEST).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lat</td><br/>
> <br/>
> <td>Last reported Latitude of the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lon</td><br/>
> <br/>
> <td>Last reported Longitude of the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RouteID</td><br/>
> <br/>
> <td>Base route name as shown on the bus. Note that the base route<br/>
> name could also refer to any variant, so a RouteID of 10A could<br/>
> refer to 10A, 10Av1, 10Av2, etc.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripEndTime</td><br/>
> <br/>
> <td>Scheduled end date and time (Eastern Standard Time) of the<br/>
> bus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripHeadsign</td><br/>
> <br/>
> <td>Destination of the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripID</td><br/>
> <br/>
> <td>Unique trip ID. This can be correlated with the data returned<br/>
> from the schedule-related methods.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripStartTime</td><br/>
> <br/>
> <td>Scheduled start date and time (Eastern Standard Time) of the<br/>
> bus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T12:40:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>VehicleID</td><br/>
> <br/>
> <td>Unique identifier for the bus. This is usually visible on the<br/>
> bus itself.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `RouteID` - _optional_ - Bus route, e.g.: 70, 10A.
    Possible values: 70.
* `Lat` - _optional_ - Center point Latitude, required if Longitude and Radius are specified.
* `Lon` - _optional_ - Center point Longitude, required if Latitude and Radius are specified.
* `Radius` - _optional_ - Radius (meters) to include in the search area, required if Latitude and Longitude are specified.

### XML - Path Details

> <h4 class="text-primary">Description</h4><br/>
> <p>For a given date, returns the set of ordered latitude/longitude points along route variant along with the list of stops served.</p><br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <tbody><br/>
> <tr><br/>
> <td>Direction0/Direction1</td><br/>
> <td><br/>
> Structures describing <a href="#Direction">path/stop</a>information.<br><br/>
> <br><br/>
> Most routes will return content in both Direction0 and Direction1 elements, though a few will return NULL for Direction0 or for Direction1.<br><br/>
> <br><br/>
> 0 or 1 are binary properties. There is no specific mapping to direction, but a different value for the same route signifies that the route is in an opposite direction.<br/>
> </td><br/>
> </tr><br/>
> <tr><br/>
> <td>Name</td><br/>
> <td>Descriptive name for the route.</td><br/>
> </tr><br/>
> <tr><br/>
> <td>RouteID</td><br/>
> <td>Bus route variant (e.g.: 10A, 10Av1, etc.).</td><br/>
> </tr><br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Direction" name="Direction">Direction0/Direction1 Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <tr><br/>
> <td style="text-decoration: line-through">DirectionNum</td><br/>
> <td><span class="text-danger">Deprecated.</span> Use the DirectionText element to denote the general direction of the route variant.</td><br/>
> </tr><br/>
> <tr><br/>
> <td>DirectionText</td><br/>
> <td>General direction of the route variant (NORTH, SOUTH, EAST, WEST, LOOP, etc.).</td><br/>
> </tr><br/>
> <tr><br/>
> <td>Shape</td><br/>
> <td><br/>
> Array containing shape point information (<a href="#ShapePoint">ShapePoint</a>).<br/>
> </td><br/>
> </tr><br/>
> <tr><br/>
> <td>Stops</td><br/>
> <td><br/>
> Array containing stop information (<a href="#Stop">Stop</a>).<br/>
> </td><br/>
> </tr><br/>
> <tr><br/>
> <td>TripHeadsign</td><br/>
> <td>Descriptive text of where the bus is headed. This is similar, but not necessarily identical, to what is displayed on the bus.</td><br/>
> </tr><br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="ShapePoint" name="ShapePoint">ShapePoint Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <tr><br/>
> <td>Lat</td><br/>
> <td>Latitude.</td><br/>
> </tr><br/>
> <tr><br/>
> <td>Lon</td><br/>
> <td>Longitude.</td><br/>
> </tr><br/>
> <tr><br/>
> <td>SeqNum</td><br/>
> <td>Order of the point in the sequence of ShapePoints.</td><br/>
> </tr><br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"> <br/>
> <a id="Stop" name="Stop">Stop Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <tr><br/>
> <td>Lat</td><br/>
> <td>Latitude.</td><br/>
> </tr><br/>
> <tr><br/>
> <td>Lon</td><br/>
> <td>Longitude.</td><br/>
> </tr><br/>
> <tr><br/>
> <td>Name</td><br/>
> <td>Stop name. May be slightly different from what is spoken or displayed in the bus.</td><br/>
> </tr><br/>
> <tr><br/>
> <td>Routes</td><br/>
> <td>String array of route variants which provide service at this stop. Note that these are not date-specific; any route variant which stops at this stop on any day will be listed.</td><br/>
> </tr><br/>
> <tr><br/>
> <td>StopID</td><br/>
> <td>7-digit regional ID which can be used in various bus-related methods. If unavailable, the StopID will be 0 or NULL.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `RouteID` - _required_ - Bus route variant, e.g.: 70, 10A, 10Av1.
    Possible values: 70.
* `Date` - _optional_ - Date in YYYY-MM-DD format for which to retrieve route and stop information.  Defaults to today's date unless specified.

### XML - Schedule

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns schedules for a given route variant for a given date.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>Direction0/Direction1</td><br/>
> <br/>
> <td><br/>
> Arrays containing trip information (<a href=<br/>
> "#Trip">Trip</a>).<br><br/>
> <br><br/>
> Most routes will return content in both Direction0 and<br/>
> Direction1 elements, though a few (especially ones which run in<br/>
> a loop, such as the U8) will return content only for Direction0<br/>
> and NULL content for Direction1.<br><br/>
> <br><br/>
> 0 or 1 are binary properties. There is no specific mapping to<br/>
> direction, but a different value for the same route signifies<br/>
> that the route is in an opposite direction.<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Name</td><br/>
> <br/>
> <td>Descriptive name for the route.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Trip" name="Trip">Trip Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">DirectionNum</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span> Use the<br/>
> TripDirectionText element to denote the general direction of the<br/>
> trip.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>EndTime</td><br/>
> <br/>
> <td>Scheduled end date and time (Eastern Standard Time) for this<br/>
> trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RouteID</td><br/>
> <br/>
> <td>Bus route variant. This can be used in several other bus<br/>
> methods which accept variants.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StartTime</td><br/>
> <br/>
> <td>Scheduled start date and time (Eastern Standard Time) for this<br/>
> trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopTimes</td><br/>
> <br/>
> <td><br/>
> Array containing location and time information (<a href=<br/>
> "#StopTime">StopTime</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripDirectionText</td><br/>
> <br/>
> <td>General direction of the trip (NORTH, SOUTH, EAST, WEST, LOOP,<br/>
> etc.).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripHeadsign</td><br/>
> <br/>
> <td>Descriptive text of where the bus is headed. This is similar,<br/>
> but not necessarily identical, to what is displayed on the<br/>
> bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripID</td><br/>
> <br/>
> <td>Unique trip ID. This can be correlated with the data returned<br/>
> from the schedule-related methods.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="StopTime" name="StopTime">StopTime Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopID</td><br/>
> <br/>
> <td>7-digit regional ID which can be used in various bus-related<br/>
> methods. If unavailable, the StopID will be 0 or NULL.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopName</td><br/>
> <br/>
> <td>Stop name. May be slightly different from what is spoken or<br/>
> displayed in the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopSeq</td><br/>
> <br/>
> <td>Order of the stop in the sequence of StopTimes.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Time</td><br/>
> <br/>
> <td>Scheduled departure date and time (Eastern Standard Time) from<br/>
> this stop. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `RouteID` - _required_ - Bus route variant, e.g.: 70, 10A, 10Av1.
    Possible values: 70.
* `Date` - _optional_ - Date in YYYY-MM-DD format for which to retrieve schedule.  Defaults to today's date unless specified.
* `IncludingVariations` - _optional_ - Whether or not to include variations.  For example, if B30 is specified, include all variations such as B30v1, B30v2, etc.
    Possible values: false, true.

### XML - Routes

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns a list of all bus route variants (patterns). For example, the 10A<br/>
> and 10Av1 are the same route, but may stop at slightly different locations.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>Routes</td><br/>
> <br/>
> <td><br/>
> Array containing route variant information (<a href=<br/>
> "#Route">Route</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Route" name="Route">Route Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Name</td><br/>
> <br/>
> <td>Descriptive name of the route variant.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RouteID</td><br/>
> <br/>
> <td>Unique identifier for a given route variant. Can be used in<br/>
> various other bus-related methods.</td><br/>
> </tr><br/>
> <br/>
> <br/>
> <tr><br/>
> <td>LineDescription</td><br/>
> <br/>
> <td>Denotes the route variant's grouping - lines are a combination of routes which lie in the same corridor and which have significant portions of their paths along the same roadways.</td><br/>
> </tr> <br/>
> </tbody><br/>
> </table>

### XML - Schedule at Stop

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns a set of buses scheduled at a stop for a given date.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>ScheduleArrivals</td><br/>
> <br/>
> <td><br/>
> Array containing scheduled arrival information (<a href=<br/>
> "#ScheduleArrival">ScheduleArrival</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Stop</td><br/>
> <br/>
> <td><br/>
> Structure describing <a href="#Stop">stop</a> information.<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="ScheduleArrival" name=<br/>
> "ScheduleArrival">ScheduleArrival Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DirectionNum</td><br/>
> <br/>
> <td>Denotes a binary direction (0 or 1) of the bus. There is no<br/>
> specific mapping to direction, but a different value for the same<br/>
> route signifies that the buses are traveling in opposite<br/>
> directions. Use the TripDirectionText element to show the actual<br/>
> destination of the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>EndTime</td><br/>
> <br/>
> <td>Scheduled end date and time (Eastern Standard Time) for this<br/>
> trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RouteID</td><br/>
> <br/>
> <td>Bus route variant identifier (pattern). This variant can be<br/>
> used in several other bus methods which accept variants. Note that<br/>
> customers will never see anything other than the base route name,<br/>
> so variants 10A, 10Av1, 10Av2, etc. will be displayed as 10A on the<br/>
> bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>ScheduleTime</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) when the bus is scheduled<br/>
> to stop at this location. Will be in YYYY-MM-DDTHH:mm:ss format<br/>
> (e.g.: 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StartTime</td><br/>
> <br/>
> <td>Scheduled start date and time (Eastern Standard Time) for this<br/>
> trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripDirectionText</td><br/>
> <br/>
> <td>General direction of the trip (e.g.: NORTH, SOUTH, EAST,<br/>
> WEST).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripHeadsign</td><br/>
> <br/>
> <td>Destination of the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripID</td><br/>
> <br/>
> <td>Trip identifier. This can be correlated with the data in our<br/>
> bus schedule information as well as bus positions.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Stop" name="Stop">Stop Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lat</td><br/>
> <br/>
> <td>Latitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lon</td><br/>
> <br/>
> <td>Longitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Name</td><br/>
> <br/>
> <td>Stop name. May be slightly different from what is spoken or<br/>
> displayed in the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Routes</td><br/>
> <br/>
> <td>String array of route variants which provide service at this<br/>
> stop. Note that these are not date-specific; any route variant<br/>
> which stops at this stop on any day will be listed.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopID</td><br/>
> <br/>
> <td>7-digit regional ID which can be used in various bus-related<br/>
> methods. If unavailable, the StopID will be 0 or NULL.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `StopID` - _required_ - 7-digit regional stop ID.
    Possible values: 1001195.
* `Date` - _optional_ - Date in YYYY-MM-DD format for which to retrieve schedule.  Defaults to today's date unless specified.

### XML - Stop Search

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns a list of nearby bus stops based on latitude, longitude, and radius.<br/>
> Omit all parameters to retrieve a list of all stops.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>Stops</td><br/>
> <br/>
> <td><br/>
> Array containing stop information (<a href="#Stop">Stop</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Stop" name="Stop">Stop Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lat</td><br/>
> <br/>
> <td>Latitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lon</td><br/>
> <br/>
> <td>Longitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Name</td><br/>
> <br/>
> <td>Stop name. May be slightly different from what is spoken or<br/>
> displayed in the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Routes</td><br/>
> <br/>
> <td>String array of route variants which provide service at this<br/>
> stop. Note that these are not date-specific; any route variant<br/>
> which stops at this stop on any day will be listed.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopID</td><br/>
> <br/>
> <td>7-digit regional ID which can be used in various bus-related<br/>
> methods. If unavailable, the StopID will be 0 or NULL.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `Lat` - _optional_ - Center point Latitude, required if Longitude and Radius are specified.
    Possible values: 38.878586.
* `Lon` - _optional_ - Center point Longitude, required if Latitude and Radius are specified.
    Possible values: -76.989626.
* `Radius` - _optional_ - Radius (feet) to include in the search area, required if Latitude and Longitude are specified.
    Possible values: 500.

### JSON - Bus Position

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns bus positions for the given route, with an optional search radius.<br/>
> If no parameters are specified, all bus positions are returned.</p><br/>
> <br/>
> <p>Note that the RouteID parameter accepts only base route names and no<br/>
> variations, i.e.: use 10A instead of 10Av1 or 10Av2.</p><br/>
> <br/>
> <p>Bus positions are refreshed approximately every <span style="text-decoration: line-through">20 to 30</span> 7 to 10 seconds.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>BusPositions</td><br/>
> <br/>
> <td><br/>
> Array containing bus position information (<a href=<br/>
> "#BusPosition">BusPositions</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="BusPosition" name="BusPosition">BusPosition<br/>
> Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DateTime</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) of last position update.<br/>
> Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:23:40).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Deviation</td><br/>
> <br/>
> <td>Deviation, in minutes, from schedule. Positive values indicate<br/>
> that the bus is running late while negative ones are for buses<br/>
> running ahead of schedule.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">DirectionNum</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span> Use the<br/>
> DirectionText for a customer-friendly description of<br/>
> direction.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DirectionText</td><br/>
> <br/>
> <td>General direction of the trip, not the bus itself (e.g.: NORTH,<br/>
> SOUTH, EAST, WEST).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lat</td><br/>
> <br/>
> <td>Last reported Latitude of the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lon</td><br/>
> <br/>
> <td>Last reported Longitude of the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RouteID</td><br/>
> <br/>
> <td>Base route name as shown on the bus. Note that the base route<br/>
> name could also refer to any variant, so a RouteID of 10A could<br/>
> refer to 10A, 10Av1, 10Av2, etc.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripEndTime</td><br/>
> <br/>
> <td>Scheduled end date and time (Eastern Standard Time) of the<br/>
> bus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripHeadsign</td><br/>
> <br/>
> <td>Destination of the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripID</td><br/>
> <br/>
> <td>Unique trip ID. This can be correlated with the data returned<br/>
> from the schedule-related methods.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripStartTime</td><br/>
> <br/>
> <td>Scheduled start date and time (Eastern Standard Time) of the<br/>
> bus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T12:40:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>VehicleID</td><br/>
> <br/>
> <td>Unique identifier for the bus. This is usually visible on the<br/>
> bus itself.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `RouteID` - _optional_ - Base bus route, e.g.: 70, 10A.
    Possible values: 70.
* `Lat` - _optional_ - Center point Latitude, required if Longitude and Radius are specified.
* `Lon` - _optional_ - Center point Longitude, required if Latitude and Radius are specified.
* `Radius` - _optional_ - Radius (meters) to include in the search area, required if Latitude and Longitude are specified.

### JSON - Path Details

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>For a given date, returns the set of ordered latitude/longitude points along<br/>
> a route variant along with the list of stops served.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>Direction0/Direction1</td><br/>
> <br/>
> <td><br/>
> Structures describing <a href="#Direction">path/stop</a><br/>
> information.<br><br/>
> <br><br/>
> Most routes will return content in both Direction0 and<br/>
> Direction1 elements, though a few will return NULL for Direction0 or for Direction1.<br><br/>
> <br><br/>
> 0 or 1 are binary properties. There is no specific mapping to<br/>
> direction, but a different value for the same route signifies<br/>
> that the route is in an opposite direction.<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Name</td><br/>
> <br/>
> <td>Descriptive name for the route.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RouteID</td><br/>
> <br/>
> <td>Bus route variant (e.g.: 10A, 10Av1, etc.).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Direction" name="Direction">Direction0/Direction1<br/>
> Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">DirectionNum</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span> Use the<br/>
> DirectionText element to denote the general direction of the route<br/>
> variant.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DirectionText</td><br/>
> <br/>
> <td>General direction of the route variant (NORTH, SOUTH, EAST,<br/>
> WEST, LOOP, etc.).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Shape</td><br/>
> <br/>
> <td><br/>
> Array containing shape point information (<a href=<br/>
> "#ShapePoint">ShapePoint</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Stops</td><br/>
> <br/>
> <td><br/>
> Array containing stop information (<a href="#Stop">Stop</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripHeadsign</td><br/>
> <br/>
> <td>Descriptive text of where the bus is headed. This is similar,<br/>
> but not necessarily identical, to what is displayed on the<br/>
> bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="ShapePoint" name="ShapePoint">ShapePoint<br/>
> Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lat</td><br/>
> <br/>
> <td>Latitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lon</td><br/>
> <br/>
> <td>Longitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>SeqNum</td><br/>
> <br/>
> <td>Order of the point in the sequence of ShapePoints.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Stop" name="Stop">Stop Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lat</td><br/>
> <br/>
> <td>Latitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lon</td><br/>
> <br/>
> <td>Longitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Name</td><br/>
> <br/>
> <td>Stop name. May be slightly different from what is spoken or<br/>
> displayed in the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Routes</td><br/>
> <br/>
> <td>String array of route variants which provide service at this<br/>
> stop. Note that these are not date-specific; any route variant<br/>
> which stops at this stop on any day will be listed.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopID</td><br/>
> <br/>
> <td>7-digit regional ID which can be used in various bus-related<br/>
> methods. If unavailable, the StopID will be 0 or NULL.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `RouteID` - _required_ - Bus route variant, e.g.: 70, 10A, 10Av1.
    Possible values: 70.
* `Date` - _optional_ - Date in YYYY-MM-DD format for which to retrieve route and stop information.  Defaults to today's date unless specified.

### JSON - Schedule

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns schedules for a given route variant for a given date.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>Direction0/Direction1</td><br/>
> <br/>
> <td><br/>
> Arrays containing trip information (<a href=<br/>
> "#Trip">Trip</a>).<br><br/>
> <br><br/>
> Most routes will return content in both Direction0 and<br/>
> Direction1 elements, though a few (especially ones which run in<br/>
> a loop, such as the U8) will return content only for Direction0<br/>
> and NULL content for Direction1.<br><br/>
> <br><br/>
> 0 or 1 are binary properties. There is no specific mapping to<br/>
> direction, but a different value for the same route signifies<br/>
> that the route is in an opposite direction.<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Name</td><br/>
> <br/>
> <td>Descriptive name for the route.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Trip" name="Trip">Trip Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td style="text-decoration: line-through">DirectionNum</td><br/>
> <br/>
> <td><span class="text-danger">Deprecated.</span> Use the<br/>
> TripDirectionText element to denote the general direction of the<br/>
> trip.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>EndTime</td><br/>
> <br/>
> <td>Scheduled end date and time (Eastern Standard Time) for this<br/>
> trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RouteID</td><br/>
> <br/>
> <td>Bus route variant. This can be used in several other bus<br/>
> methods which accept variants.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StartTime</td><br/>
> <br/>
> <td>Scheduled start date and time (Eastern Standard Time) for this<br/>
> trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopTimes</td><br/>
> <br/>
> <td><br/>
> Array containing location and time information (<a href=<br/>
> "#StopTime">StopTime</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripDirectionText</td><br/>
> <br/>
> <td>General direction of the trip (NORTH, SOUTH, EAST, WEST, LOOP,<br/>
> etc.).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripHeadsign</td><br/>
> <br/>
> <td>Descriptive text of where the bus is headed. This is similar,<br/>
> but not necessarily identical, to what is displayed on the<br/>
> bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripID</td><br/>
> <br/>
> <td>Unique trip ID. This can be correlated with the data returned<br/>
> from the schedule-related methods.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="StopTime" name="StopTime">StopTime Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopID</td><br/>
> <br/>
> <td>7-digit regional ID which can be used in various bus-related<br/>
> methods. If unavailable, the StopID will be 0 or NULL.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopName</td><br/>
> <br/>
> <td>Stop name. May be slightly different from what is spoken or<br/>
> displayed in the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopSeq</td><br/>
> <br/>
> <td>Order of the stop in the sequence of StopTimes.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Time</td><br/>
> <br/>
> <td>Scheduled departure date and time (Eastern Standard Time) from<br/>
> this stop. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `RouteID` - _required_ - Bus route variant, e.g.: 70, 10A, 10Av1, etc.
    Possible values: 70.
* `Date` - _optional_ - Date in YYYY-MM-DD format for which to retrieve schedule.  Defaults to today's date unless specified.
* `IncludingVariations` - _optional_ - Whether or not to include variations if a base route is specified in RouteID.  For example, if B30 is specified and IncludingVariations is set to true, data for all variations of B30 such as B30v1, B30v2, etc. will be returned.
    Possible values: false, true.

### JSON - Routes

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns a list of all bus route variants (patterns). For example, the 10A<br/>
> and 10Av1 are the same route, but may stop at slightly different locations.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>Routes</td><br/>
> <br/>
> <td><br/>
> Array containing route variant information (<a href=<br/>
> "#Route">Route</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Route" name="Route">Route Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Name</td><br/>
> <br/>
> <td>Descriptive name of the route variant.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RouteID</td><br/>
> <br/>
> <td>Unique identifier for a given route variant. Can be used in<br/>
> various other bus-related methods.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>LineDescription</td><br/>
> <br/>
> <td>Denotes the route variant's grouping - lines are a combination of routes which lie in the same corridor and which have significant portions of their paths along the same roadways.</td><br/>
> </tr> <br/>
> </tbody><br/>
> </table>

### JSON - Schedule at Stop

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns a set of buses scheduled at a stop for a given date.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>ScheduleArrivals</td><br/>
> <br/>
> <td><br/>
> Array containing scheduled arrival information (<a href=<br/>
> "#ScheduleArrival">ScheduleArrival</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Stop</td><br/>
> <br/>
> <td><br/>
> Structure describing <a href="#Stop">stop</a> information.<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="ScheduleArrival" name=<br/>
> "ScheduleArrival">ScheduleArrival Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>DirectionNum</td><br/>
> <br/>
> <td>Denotes a binary direction (0 or 1) of the bus. There is no<br/>
> specific mapping to direction, but a different value for the same<br/>
> route signifies that the buses are traveling in opposite<br/>
> directions. Use the TripDirectionText element to show the actual<br/>
> destination of the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>EndTime</td><br/>
> <br/>
> <td>Scheduled end date and time (Eastern Standard Time) for this<br/>
> trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>RouteID</td><br/>
> <br/>
> <td>Bus route variant identifier (pattern). This variant can be<br/>
> used in several other bus methods which accept variants. Note that<br/>
> customers will never see anything other than the base route name,<br/>
> so variants 10A, 10Av1, 10Av2, etc. will be displayed as 10A on the<br/>
> bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>ScheduleTime</td><br/>
> <br/>
> <td>Date and time (Eastern Standard Time) when the bus is scheduled<br/>
> to stop at this location. Will be in YYYY-MM-DDTHH:mm:ss format<br/>
> (e.g.: 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StartTime</td><br/>
> <br/>
> <td>Scheduled start date and time (Eastern Standard Time) for this<br/>
> trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:<br/>
> 2014-10-27T13:17:00).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripDirectionText</td><br/>
> <br/>
> <td>General direction of the trip (e.g.: NORTH, SOUTH, EAST,<br/>
> WEST).</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripHeadsign</td><br/>
> <br/>
> <td>Destination of the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>TripID</td><br/>
> <br/>
> <td>Trip identifier. This can be correlated with the data in our<br/>
> bus schedule information as well as bus positions.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Stop" name="Stop">Stop Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lat</td><br/>
> <br/>
> <td>Latitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lon</td><br/>
> <br/>
> <td>Longitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Name</td><br/>
> <br/>
> <td>Stop name. May be slightly different from what is spoken or<br/>
> displayed in the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Routes</td><br/>
> <br/>
> <td>String array of route variants which provide service at this<br/>
> stop. Note that these are not date-specific; any route variant<br/>
> which stops at this stop on any day will be listed.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopID</td><br/>
> <br/>
> <td>7-digit regional ID which can be used in various bus-related<br/>
> methods. If unavailable, the StopID will be 0 or NULL.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `StopID` - _required_ - 7-digit regional stop ID.
    Possible values: 1001195.
* `Date` - _optional_ - Date in YYYY-MM-DD format for which to retrieve schedule.  Defaults to today's date unless specified.

### JSON - Stop Search

> <h4 class="text-primary">Description</h4><br/>
> <br/>
> <p>Returns a list of nearby bus stops based on latitude, longitude, and radius.<br/>
> Omit all parameters to retrieve a list of all stops.</p><br/>
> <br/>
> <h4 class="text-primary">Response Elements</h4><br/>
> <br/>
> <table class="table table-condensed table-hover"><br/>
> <thead><br/>
> <tr><br/>
> <th class="col-md-3">Element</th><br/>
> <br/>
> <th>Description</th><br/>
> </tr><br/>
> </thead><br/>
> <br/>
> <tbody><br/>
> <tr><br/>
> <td>Stops</td><br/>
> <br/>
> <td><br/>
> Array containing stop information (<a href="#Stop">Stop</a>).<br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td colspan="2"><br/>
> <div class="text-primary" style="margin-top: 1em"><br/>
> <a id="Stop" name="Stop">Stop Elements</a><br/>
> </div><br/>
> </td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lat</td><br/>
> <br/>
> <td>Latitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Lon</td><br/>
> <br/>
> <td>Longitude.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Name</td><br/>
> <br/>
> <td>Stop name. May be slightly different from what is spoken or<br/>
> displayed in the bus.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>Routes</td><br/>
> <br/>
> <td>String array of route variants which provide service at this<br/>
> stop. Note that these are not date-specific; any route variant<br/>
> which stops at this stop on any day will be listed.</td><br/>
> </tr><br/>
> <br/>
> <tr><br/>
> <td>StopID</td><br/>
> <br/>
> <td>7-digit regional ID which can be used in various bus-related<br/>
> methods. If unavailable, the StopID will be 0 or NULL.</td><br/>
> </tr><br/>
> </tbody><br/>
> </table>

#### Input Parameters
* `Lat` - _optional_ - Center point Latitude, required if Longitude and Radius are specified.
    Possible values: 38.878586.
* `Lon` - _optional_ - Center point Longitude, required if Latitude and Radius are specified.
    Possible values: -76.989626.
* `Radius` - _optional_ - Radius (meters) to include in the search area, required if Latitude and Longitude are specified.
    Possible values: 500.

## License

**flow**ground :- Telekom iPaaS / wmata-com-bus-route-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
