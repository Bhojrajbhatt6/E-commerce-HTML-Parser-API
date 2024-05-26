# E-commerce-HTML-Parser-API

This project is a solution to an assessment task for extracting meaningful attributes from an HTML block of an e-commerce website using an open-source large language model (LLM).

## Project Overview

The objective is to develop an API that processes HTML content to extract relevant e-commerce attributes and return the information in JSON format.

## Features

- Uses BERT for Named Entity Recognition (NER)
- Extracts product names, prices, descriptions, and images
- Built with FastAPI
## Install Dependencies

pip install -r requirements.txt
## Run the API Server

uvicorn main:app --reload

## Test the API
Use a tool like Postman or curl to test the API:

curl -X POST "http://127.0.0.1:8000/extract" -H "Content-Type: application/json" -d "{\"html_content\": \"<html><head><title>Product Page</title></head><body><h1 class='product-name'>Sample Product</h1><span class='price'>$19.99</span><div class='description'>This is a sample product description.</div><img class='product-image' src='sample-product.jpg'/></body></html>\"}"

Example
Input HTML Block:

<html>
<head><title>Product Page</title></head>
<body>
<h1 class="product-name">Sample Product</h1>
<span class="price">$19.99</span>
<div class="description">This is a sample product description.</div>
<img class="product-image" src="sample-product.jpg"/>
</body>
</html>
Corresponding JSON Output:

{
  "product_names": ["Sample Product"],
  "prices": ["$19.99"],
  "descriptions": ["This is a sample product description."],
  "images": ["sample-product.jpg"]
}

