# DF: Date time conversion

## Use case

You want to convert a Parquet file to CSV for use with one of the preprocessing scripts

## Prerequisite
Parquet file containing a time-series with one or more signals

## Steps

Download the example Spark application: [parquet_to_csv.py](./example_code/parquet_to_csv.py)

Upload the code to OCI Object Storage(in case of Scala or Java, upload the compiled JAR file). Note the path to the code eg. bucket dataflow-
warehouse, root folder, file name parquet_to_csv.py.

If there are multiple files, ensure they are all in the same folder

![image info](./utils/upload_object.png)
## Create an Application

Click "Create Application"

Select the number of Executors, logging location and path to the Spark application that we just created. If you are entering the path manually, it needs to
be specified in the following format: oci://dataflow-warehouse@<compartmentID>/pivoting.py where <compartmentID> is the compartment name. Otherwise,
you can use the browser to choose an object


Add the following to the arguments:

```
--input ${input} --output ${output} --coalesce
```
<b>input</b> points to the input data source. <b>original_column</b> refers to the column to be renamed to <b>renamed_column</b>.



```
Specify path in Object Storage to store logs. These may be useful later for troubleshooting.
```
![image info](./utils/P6.png)


```
Click "Save changes" to save the Application
```
