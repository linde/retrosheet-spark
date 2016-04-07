# Retrosheet Spark

This is a simple project to create data frames in spark for the data
contained in retrosheets baseball archive. It is distributed as a
python notebook.

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
$ pip install ipython[notebook]

```

TODO - i cant recall if we need to install pyspark ...


## The finally, to run things


```bash
$ IPYTHON_OPTS="notebook" pyspark  --executor-memory 2GB 
```

Then run python notebook and execute each buffer, then query and enjoy!

## Notes

* The value for Play.countBalls and Play.countStrikes can be missing and unfortunaetly i had trouble making it nullable. so, in cases where it is missing, i supply the value -1. if you're doing something like average count or the like, exclude these records.







