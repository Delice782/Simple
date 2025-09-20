# Simple Health Check Service

## Overview

This is a simple health check service built with Flask. It monitors three endpoints and exposes their status via a /health endpoint.

The service indicates whether each endpoint is healthy (responds with HTTP 200) or unhealthy (does not respond or returns a non-200 status). This version has been tested locally.

## Endpoints Monitored

#### Name                                            
Kedebah Website                 URL: https://npontu.com

Npontu Technologies LTD         URL: https://kedebah.npontu.com

non existing service            URL: https://xyZwvu.com

## Running the Service
Run the Flask app: python simple_health_check.py

The server will start at http://127.0.0.1:5000

## Usage
Open a browser or use Postman to access http://127.0.0.1:5000/health

## Example JSON output from local testing:

{
  "Kedebah Website": "healthy",
  "Npontu Technologies LTD": "healthy",
  "non existing service": "unhealthy"
}

## Analysis: What happens when one service goes down
When one of the monitored services is down, it is reported as "unhealthy" in the /health endpoint. Other services continue to be monitored normally. This allows you to see which endpoints are working and which are not during local testing.
