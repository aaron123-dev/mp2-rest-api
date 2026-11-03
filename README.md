# MP2 REST API

This is a FastAPI app that accepts a CSV file, stores its data in memory, and returns stored rows through HTTP requests.

The endpoints that this API uses are the following: /health (checks if the API is running properly), /upload (where you upload your CSV file), /datasets/{dataset_id} - Returns up to max amount of rows for a dataset, and finally /datasets/{id}/process - Uses functions to validate and process a dataset. The processing endpoint reuses code from MP1, which was a data pipeline from a different repository that was copied into the data_pipeline/ folder. To send the processing settings, the user sends out a JSON request body. 

The middleware works by logging each request with a request ID, status code and duration.

The way the API runs its test is that it uses pytest for tasks such as uploading, processing, and retrieving.


## Running the API

~~~
python -m uvicorn main:app --reload
~~~

Then open up  http://127.0.0.1:8000/docs

Once done, do Ctrl + C in the terminal.


## Running the test

~~~
python -m pytest tests -v
~~~