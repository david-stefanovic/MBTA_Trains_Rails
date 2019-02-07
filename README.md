# MBTA_Trains_Rails
Tiny rails app that tracks MBTA departures from North and South stations

As discussed, do you think you could build a web application that shows live
Commuter Rail departure board? It should hopefully be pretty
straightforward. The application should show the upcoming departures at North
and South stations, the train destinations, the departure times, the track
numbers, and the boarding status (e.g. 'Boarding', 'All Aboard', 'Delayed').
The instructions for where to find the real-time data can be found here:
https://www.mbta.com/developers/v3-api.

Just to give you an idea, this is what the real departure board at North
Station looks like:
https://commons.wikimedi a.org/wiki/File:North_Station_departure_board.JPG.
Obviously, your application does not have to look the same.
----------------------------------------
# Forum for developers using the API
https://groups.google.com/forum/#!forum/massdotdevelopers
https://www.mbta.com/developers/v3-api

About the V3 API

The new V3 API provides fast, easy access to MBTA schedules, alerts, and real-time information.

    The V3 API uses the JSON API format, so you can get started quickly using any of the available libraries
    V3 API documentation is available using Swagger
      https://api-v3.mbta.com/docs/swagger/

You can try it out without a key, but we strongly recommend using a key early
in the development process. Keys are available for free at api-v3.mbta.com.
----------------------------------------
One of way of getting track numbers is to get a list of schedules,including trips and predictions. 

For example, something like this: `https://api-v3.mbta.com/schedules?filter[stop]=place-north&filter[direction_id]=0&include=trip,prediction`. 

For the destination you should look for `headsign` and the track number is inside
`schedule.relationships.prediction.relationships.stop.data.id`
