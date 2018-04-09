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

```bash
$ brew install apache-spark

$ virtualenv .py
$ . .py/bin/activate
$ pip install jupyter plotly pandas

```

## The finally, to run things

```bash
PYSPARK_DRIVER_PYTHON=jupyter PYSPARK_DRIVER_PYTHON_OPTS='notebook' pyspark  --executor-memory 2GB 
```

Then run python notebook and execute each buffer, then query and enjoy!

## Notes

* really need to partition







