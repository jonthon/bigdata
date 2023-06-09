# BigData

DESCRIPTION:
-----------
+ system interfaces: ```BigData```, ```Chunks```, ```ParallelRepeat```, and ```ParallelOnce```
+ pandas interfaces: ```Pandas```, ```BigDataPd```, ```ChunksPd```, ```ParallelPdRepeat```, ```ParallelPdOnce```, ```SamplePd```, and ```DropDuplicatesPd```

This package implements interfaces for use on huge data files of any format (ie. json, html, csv, table, etc) supported by data libraries like ```pandas```, ```numpy```, ```polars```, etc. ```pandas``` loading and dumping (```read_*``` and ```obj.to_*```) interfaces are primarily used in this package. However, customization is more than welcomed to implement other data library interfaces. The low level interfaces (system intefaces) mentioned above are the recommended interfaces to customize for a specific data library. See pandas interfaces mentioned above in the ```__init__.py``` for an example implementation.

It uses system interfaces to simplify data management; thus, a user only needs to perform specific data operations on files of any size that a running machine can hold. These specific data operations include fetching data, cleaning, reshaping, aligning, aggregating, analysing, visualising, etc. 

Data handling in this package is approached in two main ways, either from a huge file or from chunks of data. ```BigData*``` types are used for huge single files while ```Chunks*``` types are used for chunks of data files. ```Parallel*``` types customize ```Chunks``` class, and they loop through a hierarchy of data file chunks in sorted order either repeatedly or once. 
A good example is ```DropDuplicatesPd``` that drops duplicated rows from chunks of data files. All rows from all chunks of data become unique to each other after running ```DropDuplicatesPd```. 

For more flexibility, customize the pandas specific interfaces mentioned earlier and perform specific data operations using pandas.


USAGE:
-----
This file's ```if __name__ == '__main__':``` statement block in ```__init__.py``` implements unittests for this package's main logic (handling big files or chunks of data). In these tests, pandas specific interfaces are customized and invoked as desired. Please, see code file (```__init__.py```) for example usages.


EXAMPLES:
--------
