# Arff Conversion

[ARFF](https://waikato.github.io/weka-wiki/formats_and_processing/arff/) is a file format built from the ground up for data science.  This is because it describes the training data, schema and target data with lots of attributes that don't come when you just have a csv or json. This is great but `ARFF` files are very hard to use in all other languages besides Java. 

For instance, Scipy has function to [load ARFF files](https://docs.scipy.org/doc/scipy/reference/generated/scipy.io.arff.loadarff.html#scipy-io-arff-loadarff) but it comes with some major caveats. [link](https://docs.scipy.org/doc/scipy/reference/generated/scipy.io.arff.loadarff.html#scipy-io-arff-loadarff)

>This function should be able to read most arff files. Not implemented functionality include: 
>
>    date type attributes
>
>    string type attributes
>
>It can read files with numeric and nominal attributes. It cannot read files with sparse data ({} in the file). However, this function can read files with missing data (? in the file), representing the data points as NaNs.


## Use
This library will use JAVA, ARFFs native language, to convert the ARFFS to JSON. The JSON data structure matches the ARFF so there is a header section describing the attributes and a "data" section that actually contains the data. This is a dump wrapper around Weka JSONSaver.

You can use it like this


`./gradlew run --args="PATH_TO_ONE_FILE.arff PATH_TO_ANOTHER_FILE.arff"`

and those files will get converted to json in the same directory as the original file. 

Enjoy
