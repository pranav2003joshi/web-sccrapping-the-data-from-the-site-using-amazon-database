# web-sccrapping-the-data-from-the-site-using-amazon-database
This project will give you the basics of data scrapping from amazon database 
This code extracts the data from amazon S3 bucket this code will only work if you know the xml content of the S3 bucket

1. **XML Content Extraction:**
   - The code assumes the existence of an XML document containing information about files stored on Amazon S3. This XML content is stored in the variable `xml_content`.

2. **XML Parsing:**
   - The XML content is parsed using the `ElementTree` module. The `ET.fromstring(xml_content)` method is used to create an XML element tree, and the root of the tree is stored in the variable `root`.

3. **File Name Extraction:**
   - An array `file_names` is created to store the keys (file names).
   - Using a loop, the code finds all `<Key>` elements in the XML content and appends their text (file names) to the `file_names` array.

4. **Printing File Names:**
   - The array of file names is printed to the console using `print(file_names)`.

5. **Image Download:**
   - The code uses the `requests` library to download images from Amazon S3. It assumes a base URL for the images (`base_url`).

6. **Folder Creation:**
   - A folder named `downloaded_images` is created to store the downloaded images if it doesn't already exist.

7. **Image Download Loop:**
   - For each file name in the `file_names` array, the code constructs the full image URL using the `base_url` and the file name.
   - It sends a GET request to the image URL and checks if the response status code is 200 (OK).
   - If successful, the image content is saved to a file in the `downloaded_images` folder.

8. **Download Status Printing:**
   - The code prints a message indicating whether each image was successfully downloaded or if there was a failure.

9. **Completion Message:**
   - After the loop, a final message is printed to indicate that the download process has been completed.
