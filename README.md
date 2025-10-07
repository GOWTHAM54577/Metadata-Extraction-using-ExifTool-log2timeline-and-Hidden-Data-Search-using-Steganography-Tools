# Metadata-Extraction-using-ExifTool-log2timeline-and-Hidden-Data-Search-using-Steganography-Tools
## AIM:
To extract metadata, perform timeline analysis, and search for hidden data using forensic tools like ExifTool, log2timeline, and steganography detection tools.
## REQUIREMENTS
- **Operating System:** Kali Linux (preferred) or any Linux distro with forensic tools
- **Tools:**
     -  ExifTool – For metadata extraction
     -  plaso/log2timeline – For timeline analysis
- **Steganography tools:** steghide, zsteg, binwalk
- **Test Data:** Image, video, and document files (some with embedded hidden data)

## ARCHITECTURE DIAGRAM:

```mermaid
flowchart TD
    A[Sample Files - Images, Videos, Documents] --> B[Metadata Extraction with ExifTool]
    B --> C[Event Timeline Creation with log2timeline]
    C --> D[Hidden Data Search with Steganography Tools]
    D --> E[Evidence Analysis and Documentation]
```

## DESIGN STEPS:
### Step 1:
Use exiftool to extract metadata from files such as images, documents, and videos.

### Step 2:
Use log2timeline and plaso to create and analyze event timelines from system logs and file metadata.

### Step 3:
Apply steganography detection tools like steghide, zsteg, or binwalk to uncover hidden data in media files.

## PROGRAM:
| Step | Action                  | Tool                 | Output                           |
| ---- | ----------------------- | -------------------- | -------------------------------- |
| 1    | Extract file metadata   | ExifTool             | Metadata fields, GPS, timestamps |
| 2    | Generate event timeline | log2timeline / plaso | CSV/HTML timeline                |
| 3    | Search for hidden data  | steghide / binwalk   | Extracted hidden files           |
| 4    | Document findings       | Manual report        | Investigation record             |


## OUTPUT:
### A. Using ExifTool – for file metadata
- **Install:**
```bash
sudo apt update
sudo apt install exiftool -y
```
<img width="1273" height="449" alt="image" src="https://github.com/user-attachments/assets/26f5b116-aa49-4385-878a-c5602b4962d2" />

- **Extract metadata from a file:**
```bash
exiftool image.jpg
```
<img width="488" height="391" alt="image" src="https://github.com/user-attachments/assets/64626f5b-ecd7-4bda-982a-6dd0cfff28fe" />


- **Batch process a folder:**
```bash
exiftool -r /path/to/folder
```
<img width="482" height="394" alt="image" src="https://github.com/user-attachments/assets/1f57ec83-dea2-4bff-93bb-b393018319eb" />

- **Useful flags:**
  
- ```-G: Show metadata group```

- ```-time:all: Show only timestamps```

- ```-GPSLatitude -GPSLongitude: Extract GPS data```


<img width="479" height="386" alt="image" src="https://github.com/user-attachments/assets/639cfec3-3b4d-45d4-93f4-329f312c6fb3" />




### install log2timeline
```
sudo apt install plaso -y
```
<img width="1268" height="539" alt="image" src="https://github.com/user-attachments/assets/f725b59c-6b5b-4e21-aa9a-33348bd77410" />


```
sudo apt install steghide -y
```
<img width="992" height="396" alt="image" src="https://github.com/user-attachments/assets/aecc5d5a-6d46-4867-9da3-99a494644319" />

- **Embed data**
```
steghide embed -cf /home/kali/Downloads/wallpaper.jpg -ef /home/kali/Downloads/secret.txt
```

<img width="985" height="476" alt="image" src="https://github.com/user-attachments/assets/ded27cff-621b-4277-a018-b01da80b1069" />




- **Extract hidden data:**
```
steghide extract -sf hidden.jpg

```


<img width="992" height="462" alt="image" src="https://github.com/user-attachments/assets/4c7a6126-3fde-49d3-8d11-326ef94190ea" />



### Using binwalk – for file analysis
```bash
sudo apt install binwalk -y
binwalk suspicious.jpg
```
<img width="983" height="216" alt="image" src="https://github.com/user-attachments/assets/c286878f-c754-4682-b522-a74e4c8b01c8" />

```bash
binwalk /home/kali/Downloads/wallpaper.jpg
```

<img width="396" height="49" alt="image" src="https://github.com/user-attachments/assets/ebc7b6c8-23c1-4862-a559-11a18fbb54da" />




## RESULT:
Metadata was successfully extracted, timeline analysis was completed, and hidden data was identified using steganography tools.
