# Image Processing Pipeline

## Description
This project automates an end-to-end image processing workflow that includes downloading images, converting them to grayscale, resizing, compressing them into a ZIP file, and emailing the processed images. The pipeline is designed to work efficiently with Python scripts, offering flexibility with customizable parameters.

## Project Overview
The pipeline executes the following tasks:
1. **Download Images**: Downloads images from the internet based on a given keyword.
2. **Convert to Grayscale**: Converts the downloaded images to grayscale.
3. **Resize Images**: Scales images by a specified percentage.
4. **Compress Files**: Archives the processed images into a ZIP file.
5. **Send Email**: Emails the ZIP file as an attachment to a specified recipient.

## Files in the Project
- **`download.py`**: Downloads images based on a search keyword.
- **`grayscaleconvert.py`**: Converts images to grayscale.
- **`scale.py`**: Resizes images based on a specified percentage.
- **`zip.py`**: Compresses processed images into a ZIP file.
- **`sendEmail.py`**: Sends the ZIP file to an email recipient.
- **`pipeline.py`**: Runs the entire image processing pipeline.
- **`main.py`**: Simplifies the pipeline with predefined parameters.

## Usage

### Running the Entire Pipeline
To execute the complete workflow:
```bash
python pipeline.py <keyword> <max_num> <downstorage_dir> <constorage_dir> <scale_percent> <scstorage_dir> <zipstorage_dir> <recipient_email>
```
Where:
- `<keyword>`: Search term for downloading images.
- `<max_num>`: Maximum number of images to download.
- `<downstorage_dir>`: Directory to store downloaded images.
- `<constorage_dir>`: Directory to save grayscale images.
- `<scale_percent>`: Percentage to resize the images.
- `<scstorage_dir>`: Directory to save resized images.
- `<zipstorage_dir>`: Directory path for the ZIP file (without extension).
- `<recipient_email>`: Email address to send the ZIP file.

#### Example:
To download 10 images of "cats," convert them to grayscale, resize them to 50%, and email the ZIP file:
```bash
python pipeline.py cats 10 downloaded_images grayscale_images 50 resized_images image_archive recipient@example.com
```

### Running Predefined Workflow
For a simplified pipeline with predefined parameters:
```bash
python main.py
```
This script:
1. Downloads 20 images of "motorbike" into the `downloaded_images` directory.
2. Converts them to grayscale and saves them in the `grayscale_images` directory.
3. Resizes the images to 50% and saves them in the `resized_images` directory.
4. Archives them into a ZIP file named `Finalzip.zip`.
5. Emails the ZIP file to `email@example.com`.

### Individual Script Execution
Each step can be executed independently:
1. **Download Images**:
   ```bash
   python download.py <max_num> <keyword> <output_folder>
   ```
2. **Convert to Grayscale**:
   ```bash
   python grayscaleconvert.py <input_folder> <output_folder>
   ```
3. **Resize Images**:
   ```bash
   python scale.py <input_folder> <output_folder> <scale_percent>
   ```
4. **Compress Files**:
   ```bash
   python zip.py <input_folder> <zip_file_name>
   ```
5. **Send Email**:
   ```bash
   python sendEmail.py <zip_file_path> <recipient_email>
   ```

## Requirements
- **Python 3.x**
- Required Libraries:
  - `icrawler`
  - `opencv-python`
  - `yagmail`

Install dependencies using:
```bash
pip install -r requirements.txt
```

## Example Directory Structure
```plaintext
ImageDownloader/
├── files/
│   ├── download.py
│   ├── grayscaleconvert.py
│   ├── scale.py
│   ├── zip.py
│   ├── sendEmail.py
├── pipeline.py
├── main.py
├── requirements.txt
```

## Troubleshooting
- **Empty ZIP Files**: Ensure all processing steps are executed correctly before zipping.
- **Email Errors**: Check email server settings and authentication credentials.
- **File Not Found**: Verify folder paths and directory structure.

## License
This project is licensed under the MIT License.

