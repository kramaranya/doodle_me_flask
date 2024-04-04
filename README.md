# Doodle Me - A Drawing Prediction App

Doodle Me is a Flutter-based application designed to predict drawings using a convolutional neural network model. This project showcases how to preprocess user-drawn images on a canvas and use a trained model to predict the drawing's class.

## Features

- Flask API for preprocessing drawings and predicting their classes.
- Utilizes OpenCV for image manipulation and preprocessing.
- Integration with a machine learning model for drawing prediction.
- Deployment on Heroku for easy access and testing.

## Prerequisites

Before you begin, ensure you have met the following requirements:
- Python 3.6 or later is installed on your system.
- You have a Heroku account for deploying the application.

## Deploying to Heroku

This application is already deployed to Heroku at the following URL: [https://doodle-me-flask-64dde020fc72.herokuapp.com/preprocess](https://doodle-me-flask-64dde020fc72.herokuapp.com/preprocess)

## Usage

You can use the /preprocess endpoint to send drawing data for prediction. Here's an example of how to make a request using `curl`:
```
curl -X POST -H "Content-Type: application/json" -d '{"strokes": [[[0, 1, 2], [0, 1, 2]]], "canvasSize": {"width": 393, "height": 393}}' https://your-app-name.herokuapp.com/preprocess
```

Replace your-app-name with the name of your Heroku app or use the live [URL](https://doodle-me-flask-64dde020fc72.herokuapp.com/preprocess) to test the deployed application:
```
curl -X POST -H "Content-Type: application/json" -d '{"strokes": [[[0, 1, 2], [0, 1, 2]]], "canvasSize": {"width": 393, "height": 393}}' [https://your-app-name.herokuapp.com/preprocess](https://doodle-me-flask-64dde020fc72.herokuapp.com/preprocess)
```
As a result, you will receive a preprocessed and normalized drawing in the following format:
```
[ 
  [  // First stroke 
    [x0, x1, x2, x3, ...],
    [y0, y1, y2, y3, ...],
  ],
  [  // Second stroke
    [x0, x1, x2, x3, ...],
    [y0, y1, y2, y3, ...],
  ],
  ... // Additional strokes
]
```
This output format represents the preprocessed drawing, where each array corresponds to a stroke on the canvas. Each stroke contains two arrays: the first for the x-coordinates and the second for the y-coordinates of the points in the stroke.



