# AdobeGensolve Round 2

This is a Python application that processes 2D shape data from a CSV file, identifies and regularizes shapes (such as lines, circles, and quadrilaterals), and outputs the results as an SVG image. This tool can be useful for visualizing geometric data, automating shape detection, and refining vector graphics.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Docker Usage](#docker-usage)

## Features
- Shape Detection: Automatically detects and regularizes shapes such as straight lines, circles, and quadrilaterals.
- SVG Output: Generates high-quality SVG files from the input data, suitable for further editing or use in web applications.
- Visualization: Displays the output image as a PNG using matplotlib for immediate visualization.
- Flexible Input: Reads input data from CSV files, making it easy to integrate with other data processing pipelines.

## Usage
For Running the Application Locally

Clone the Repository
git clone https://github.com/yourusername/AdobeGensolve.git

cd AdobeGensolve

Set Up the Environment
It's recommended to use a virtual environment:

python3.11 -m venv venv

source venv/bin/activate

Install Required Dependencies
Install the necessary Python packages using:
pip install -r requirements.txt

Code:
python src/shape_regularization.py

Dataset:
dataset/frag0.csv 

Output:
output/output.svg

## Docker Usage
Steps for Running With Docker
docker build -t shape-regularization 
mkdir -p output  # Ensure output directory exists
docker run --rm -v $(pwd)/output:/app/output shape-regularization

Sharing the Docker Image
Push to Docker Hub
docker tag shape-regularization yourusername/yourapp:latest

Push to Docker Hub
docker push yourusername/yourapp:latest

Pull and Run the Image

Others can use the following command to run the image:
docker pull yourusername/yourapp:latest
docker run --rm -v $(pwd)/output:/app/output yourusername/yourapp

Sharing the Source Code

Share the repository URL. Others can clone it, build the image, and run it:
git clone https://github.com/vishwajeetfr/AdobeGensolve.git
cd AdobeGensolve
docker build -t shape-regularization .
docker run --rm -v $(pwd)/output:/app/output shape-regularization
Distributing as a Docker Archive

Save and load the image as a .tar file:
Export the Image
docker save -o shape-regularization.tar shape-regularization

Load the Image
docker load -i shape-regularization.tar
docker run --rm -v $(pwd)/output:/app/output shape-regularization
