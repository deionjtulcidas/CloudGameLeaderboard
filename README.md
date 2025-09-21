## Pitt Panthers Cloud Leaderboard

This project is a cloud-hosted leaderboard where players can submit scores and view rankings through a web interface. It was built using AWS services including S3 for hosting, API Gateway for routing, Lambda for serverless backend logic, and DynamoDB for storage.

The goal was to create a serverless application that demonstrates how data can flow from a user-facing website into AWS infrastructure, update a database, and then be displayed back to the user in real time.

## Features

Static website hosted on Amazon S3

REST API built with API Gateway

Lambda functions for processing score submissions

DynamoDB table for storing and retrieving leaderboard data

Basic CORS setup to allow the site to communicate with the API

## Challenges

While working on this project, I ran into several issues with API Gateway deployments, CORS errors, and getting Lambda and DynamoDB to connect correctly. These were resolved by carefully configuring API Gateway routes and enabling CORS for the right methods and origins.

## How it works

The frontend is a simple HTML and JavaScript site styled with Pitt Panthers colors.

Users submit their name and score through the form.

The request is sent to the API Gateway endpoint.

A Lambda function processes the request and stores the score in DynamoDB.

The leaderboard fetches updated scores and displays them on the site.
