# Retrosheet Spark

This is a simple project to create data frames in spark for the data
contained in retrosheets baseball archive. It is distributed as a
python notebook.

This project owes a lot to the helpful comment here:
http://stackoverflow.com/questions/31227363/creating-spark-data-structure-from-multiline-record


## Getting the retrosheets data

```bash
$ mkdir retrosheet-data
$ cd retrosheet-data
$ for yyyy in `seq 1910 10 2010`; do echo getting $yyyy; wget http://www.retrosheet.org/events/${yyyy}seve.zip; done
$ for yyyy in `seq 1910 10 2010`; do mkdir ${yyyy}seve; done
$ for yyyy in `seq 1910 10 2010`; do unzip -d ${yyyy}seve  ${yyyy}seve.zip; done
```

## Some notes on getting up and going...

This verion targets the latest python3 in brew at the moment (Python
3.6.5) and spark v2.3.0 running pyspark within jupyter.. You can do
something akin to the following to get them installed.


```bash
$ brew install apache-spark
$ brew install python
$ pip3 install virtualenv
$ virtualenv .py
$ . .py/bin/activate
$ pip install jupyter 
```

if you want to do the plotting example in [Raw event examples.ipynb], then also install the following:

```bash
$ pip install plotly 
```

## The finally, to run things

```bash
PYSPARK_DRIVER_PYTHON=jupyter PYSPARK_DRIVER_PYTHON_OPTS='notebook' pyspark  --executor-memory 2GB 
```

Then run python notebook and execute each buffer, then query and enjoy!

## Notes








