9/26

To do list​

·Figure out how to use the interactive segmentation model.​

·Load and run the web mapping data locally.

10/3
Done

·Make the segment model in Google Colab notebook work.​

·tutorial https://samgeo.gishub.org/examples/input_prompts/​

·Figure out how to use the interactive segmentation model.​

·Load and run the web mapping data locally.​

To-do list​

·Find out why the vector tiles do not show up.​

·Play with the interactive segmentation model, and test it in detail.​

·Try PMtiles approach to address the vector tile loading issue.​

10/24

To do list:​

·Remake the vector tile locally using process​

·Try PMtiles​

·Make a markdown document on GitHub, and push all the results onto it after made everything work locally​

Progress:

Fixed the problem of vector patch display. 

  Got the vector tiles showing up with http.server (back into the readme file)​
  
  python -m http.server​
  
  --Serving HTTP on :: port 8000 (http://[::]:8000/) …"​
  
  http://[::]:8000/ access invalid​
  
  Solved by replace by "http://localhost:8000"
  
Problems:

  Tippecanoe runs only on unix environments like MacOS and Linux ​
  
  Ubuntu is required for Tippecanoe installation ​
  

11/2

To do list

·Try PM tiles instead of vector tiles.​

·Working with SAM, do the segmentation in a data frame.​

11/7

To do list:

pick up last week's tasks.

Process:
  Benifit of pmtiles:
  
    Single File Archive: Unlike traditional tilesets that store each tile as an individual file, PMTiles packs the entire tileset into a single, optimized file. 
    This reduces the number of HTTP requests needed to fetch tiles.

    HTTP Range Requests: PMTiles leverages HTTP range requests to fetch only the parts of the file necessary to render the current view, rather than downloading 
    the entire file.
    
    Cloud Storage Compatibility: The single-file format is highly compatible with cloud object stores like Amazon S3, which can efficiently serve range requests.
    
    Multi-resolution Storage: PMTiles stores tiles at multiple zoom levels, allowing applications to request the appropriate resolution based on the zoom level of 
    the map view.
    
    Tooling: The PMTiles project provides tools for converting existing MBTiles archives to PMTiles, serving PMTiles archives over HTTP, and integrating PMTiles 
    into web applications.
    
    Web Integration: PMTiles can be used on the web by utilizing JavaScript libraries that support the format. This allows for seamless integration into existing
    web mapping applications.

