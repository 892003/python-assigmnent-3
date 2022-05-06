
Glad you asked! Dask is a free and open-source library for parallel computing in Python. Dask helps you scale your data science and machine learning workflows. Dask makes it easy to work with Numpy, pandas, and Scikit-Learn, but that’s just the beginning. Dask is a framework to build distributed applications that has since been used with dozens of other systems like XGBoost, PyTorch, Prefect, Airflow, RAPIDS, and more. It’s a full distributed computing toolbox that fits comfortably in your hand.

If you have larger-than-memory data, you can use Dask to scale up your workflow to leverage all the cores of your local workstation, or even scale out to the cloud.

This article will discuss:

How Dask can help parallelize your data science computations,
Behind-the-scenes workings of Dask with schedulers and workers, and
Dask’s diagnostics dashboard and resources for scaling to the cloud.

A prominent feature of Dask is its familiar API. As Matthew Rocklin, the creator of Dask wrote in A Brief History of Dask:

“One pain point we heard time and time again was that people worked with data that fit comfortably on disk but that was too big for RAM, and accelerating NumPy was a common feature request to Continuum/Anaconda at the time. To this end, the purpose of Dask was originally to parallelize NumPy so that it could harness one full workstation computer, which was common in finance shops at the time. There were two technical goals, and a social goal:

Technical: Harness the power of all of the cores on the laptop/workstation in parallel;
Technical: Support larger-than-memory computation, allowing datasets that fit on disk, but not in RAM;
Social: Invent nothing. We wanted to be as familiar as possible to what users already knew in the PyData stack.import numpy as np
import dask.array as da

5.a = da.from_array(
    np.array([
        [ 1,  2,  3,  4],
        [ 5,  6,  7,  8],
        [ 9, 10, 11, 12],
        [13, 14, 15, 16]
    ]),
    chunks=(2, 2)
    
import json
 
a = '{"name": "Bob", "languages": "English"}'
y = json.loads(a)
 
print("JSON string = ", y)
print()
f = open ('data.json', "r")
 
data = json.loads(f.read())

for i in data['emp_details']:
    print(i)
f.close()
