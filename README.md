# Fluid API Documentation

Fluid is still in beta and the api is still evolving. Please check back here for the most up to date information on our api.

## The API Format

The API accepts only JSON requests. Please make sure you're setting `Content-Type: application/json`in your request header. Each request returns eith a JSON-encoded body or a XML-encoded body.

The result of each action is communicated via standard HTTP response codes.

Times and dates use the ISO 8601 standard.

Please do note that the times and dates stores in UTC(GMT), on return the data is set into the appropriate timezone according to the setting in user profile. 3rd party applications should make sure that they are using correct timezones and also consider daylight saving (where applicable).

[insert information regarding rate limiting]

## Example requests

The example requests here are done using a command line called [cURL](http://en.wikipedia.org/wiki/CURL). If you want to try the requests out yourself, you can download cURL from [here](http://curl.haxx.se/download.html). It is available for all operating systems.

For Ubuntu installing cURL is very easy:

`sudo apt-get install curl`

For MAC cURL is already installed.

## API token

Since we are still in beta, please forward all requests for an API token to support@choosefluid.com. Please place API request as the subject line of your email.

