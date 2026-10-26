# Analysis-of-the-Disk-Structure-using-Sleuth-Kit
### NAME : SUBHASHRI R 
### REG NO: 212223230219
## AIM:
To analyze the disk structure of a given disk image using Sleuth Kit tools in Kali Linux.

## REQUIREMENTS
- **Operating System**: Windows 10/11 or Kali Linux
- **Tools**:  
  - [The Sleuth Kit for Windows](https://sleuthkit.org/)  
  - Optional GUI: [Autopsy Forensic Browser](https://www.autopsy.com/)
- **Test Data**: Disk image file (`disk.dd`, `disk.img`, `.E01`)

## ARCHITECTURE DIAGRAM
```mermaid



<img width="852" height="787" alt="image" src="https://github.com/user-attachments/assets/3295b0e1-930c-4ef4-b426-1f0e040e01cf" />

```
## DESIGN STEPS:
### Step 1:
- Obtain or create a disk image file (e.g., disk.dd) to analyze.
- Open the terminal in Kali Linux.

### Step 2:
Use Sleuth Kit tools like:
 - mmls → Examine the partition layout.
 - fsstat → View file system details.
 - fls → Get file listing.
 - icat → Recover files using inode numbers.
### Step 3:
Interpret the output to understand:
 - Partition table layout
 - File system metadata (block size, creation time, etc.)
 - Deleted and allocated files
 - Inode-based file recovery

## PROGRAM:
Sleuth Kit Disk Analysis Commands
### Partition Analysis
```bash
mmls disk.dd
```
### File System Metadata
```bash
fsstat -o 2048 disk.dd
```
### File Listing
```bash
fls -o 2048 disk.dd
```
### File Recovery
```bash
icat -o 2048 disk.dd 4 > recovered_file.txt
```
- Recovers the file associated with inode 4.
## SAMPLE WORKFLOW (Windows)
```bash
# Step 1: View partitions
mmls.exe C:\forensics\disk.dd

# Step 2: View file system details
fsstat.exe -o 2048 C:\forensics\disk.dd

# Step 3: List files
fls.exe -r -o 2048 C:\forensics\disk.dd

# Step 4: Recover a file
icat.exe -o 2048 C:\forensics\disk.dd 6 > C:\forensics\image.jpg
```
## OUTPUT:


Disk Structure Analysis Results


<img width="228" height="64" alt="image" src="https://github.com/user-attachments/assets/3bb1a17e-9a88-4028-a04a-0816fdbf2fa2" />

<img width="508" height="96" alt="image" src="https://github.com/user-attachments/assets/3f2b6d13-13cc-4460-bfc4-5ca2fc1891d7" />

<img width="550" height="240" alt="image" src="https://github.com/user-attachments/assets/34e2251c-38ee-4d99-b0b9-00dd8c12ffb7" />

<img width="673" height="940" alt="image" src="https://github.com/user-attachments/assets/8f196020-c709-4374-8727-b28ec94d6767" />

<img width="1061" height="121" alt="image" src="https://github.com/user-attachments/assets/7d592a3d-315a-44bd-95fb-84dcc70ecf9a" />

<img width="962" height="849" alt="image" src="https://github.com/user-attachments/assets/e6f43525-9abd-4477-9573-df941f0cb733" />

<img width="585" height="633" alt="image" src="https://github.com/user-attachments/assets/8e41763e-c90a-4df0-b79f-d43f52206ce4" />



## RESULT:
The analysis was performed successfully using Sleuth Kit, and the disk structure was understood in detail.
