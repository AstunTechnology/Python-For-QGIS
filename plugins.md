# Writing Plugins

+ [Creating a simple plugin](https://astuntechnology.github.io/qgis-tutorials/html/en/docs/building_a_python_plugin.html)

  There are some issues with the AppStream implementation and the S3 buckets
  used to store your work in a permanent way. So you will need to save your
  plugin not in the `.qgis2` folder of your home folder but in the
  `C:\Users\PhotonUser` folder.
  
  Then open an `OSGEO4W Shell` and set the `QGIS_PLUGINPATH` variable to point
  to the folder you just created. 

      QGIS_PLUGINPATH=C:\Users\PhotonUser\plugins

  and then run qgis from the same command shell, by typing `qgis-appstream.bat`

+ [Writing a processing plugin](https://astuntechnology.github.io/qgis-tutorials/html/en/docs/processing_python_scripts.html)

