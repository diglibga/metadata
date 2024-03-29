### Conversion and reconciliation:

1. Image resize
   * Looks in the folder form input, converts png/jpeg/jp2 to max 300x300 jpgs
   * Extracts a page from a pdf and converts to max 300x300 jpg
   * ***THIS WILL PERMANENTLY DELETE THE ORIGINAL FILES WITH NO ABILITY TO RECOVER***
     * Use at your own risk
   * Dependancies: pypdfium2, pillow
2. XmlToCsv
   * Will transform ActiveXML from dlgadmin to a csv with record_id, url, url2
   * Url is direct path to thumbnail
   * Url2 is path to object
   * Urls may be the same if there is no path to thumbnails
   * Dependancies: pandas, xml elementtree
3. Reconciliation
   * Counts the number of records from a dlg-thumbnails directory listing

### Image Downloads
1. img_dl_cdm.py -- Image retrieval and download (requires XmlToCsv format)
   * Creates a folder with the same name as the csv
   * Downloads thumbnail if found and names it with record_id
   * Download full size first image or whole object, whichever is accessible
2. img_dl_digitalcommons.py -- Image retrieval and download (requires XmlToCsv format)
   * Creates a folder with the same name as the csv
   * Downloads thumbnail if found and names it with record_id
   * Download full size first image or whole object, whichever is accessible
3. img_dl_generic.py
   * Base script without DAMS specific modifications
   * Creates a folder with the same name as the csv
   * Downloads thumbnail if found and names it with record_id
4. __img_dl_general.py__
   * __Will take whatever csv you feed it, figure out which DAMS script to use (based on record_id repo code) and run that script__
   * __The repo will need to be added to the dictionary the first time we generate thumbs for it__
5. img_dl_islandora.py -- Image retrieval and download (requires XmlToCsv format)
   * Creates a folder with the same name as the csv
   * Downloads thumbnail if found and names it with record_id
6. img_dl_omeka.py -- Image retrieval and download (requires XmlToCsv format)
   * Creates a folder with the same name as the csv
   * Downloads thumbnail if found and names it with record_id
   * Download full size first image or whole pdf, whichever is accessible
   * Currently, works for Columbus and FCS flavors of Omeka

   
