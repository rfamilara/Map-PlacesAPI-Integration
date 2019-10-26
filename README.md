# Map-PlacesAPI-Integration

This document explains how we begin testing the API with json array then with PLaces API to GET venue information. The venue category was set as pizza while the filter was initially narrowed down to the state of Chicago; hence, the latitude of 41.878 and longitude -87.630.

We signed up to https://developer.foursquare.com/docs/api then acquired the client_ID and client_secret then perform initial tests through POSTMAN and Code sandbox. Initial actions performed were as follows:

#1- retrieves 10 pizza places and displays a json array
json array of initial 10 sample pizza places retrieved(Used POSTMAN to GET and test):           https://api.foursquare.com/v2/venues/searchclient_id=AAK5YW24JUNRUTVSMMRAVVDAJQB2YN3K1IG1XTWP5NYDA1LB&client_secret=WS4TNCUOCJVEIXCZ0ALYXMZ5XJB0SQ11CPICSP2VPCJ1IXIY&v=20190425&near=chicago&intent=checkin&limit=10&categoryId=4bf58dd8d48988d1ca941735 


#2- retrieves a pizza place by name and displays the info we want

https://api.foursquare.com/v2/venues/search?client_id=AAK5YW24JUNRUTVSMMRAVVDAJQB2YN3K1IG1XTWP5NYDA1LB&client_secret=WS4TNCUOCJVEIXCZ0ALYXMZ5XJB0SQ11CPICSP2VPCJ1IXIY&v=20190425&ll=41.878,-87.630&near=chicago&intent=browse&radius=10000&query=pizza&limit=10

Clean the “GET” query which generated similar expected information output as item#1. Currently finding a way to filter and simplify into just what we need; thus, creating an initial code for pizaa place markers which we'll then integrate with Google Map API later on.

getVenues = () => {
    const endPoint = "https://api.foursquare.com/v2/venues/explore?"
    const parameters = {
      client_id: "AAK5YW24JUNRUTVSMMRAVVDAJQB2YN3K1IG1XTWP5NYDA1LB",
      client_secret: "WS4TNCUOCJVEIXCZ0ALYXMZ5XJB0SQ11CPICSP2VPCJ1IXIY",
      query: "pizza",
      near: "Chicago",
      v: "20190425"
    }


