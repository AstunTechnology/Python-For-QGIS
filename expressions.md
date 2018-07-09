# Python Expressions

## Exercise 

[Using Custom Python Expression
Functions](https://astuntechnology.github.io/qgis-tutorials/html/en/docs/custom_python_functions.html)


**NOTE**: In a change from QGIS 2.14 to 2.18 it is necessary to add
`usesgeometry=True` to the decorator in the QGIS custom select function to force
QGIS to pass the feature's geometry to the function. So 

    @qgsfunction(args="auto", group='Custom')

becomes

    @qgsfunction(args="auto", group='Custom', usesgeometry=True)
