
# 🕵️‍♀️ Investigating P2P Data Leakage at Beat Step

This repository contains the **digital forensic investigation report, presentation, and a supporting Python script** related to a data leakage incident at *Beat Step*, a company specializing in sound effects for media productions.

## 📁 Contents

```
digital-forensics-p2p-leakage/
├── README.md
├── Report/
│   ├── A Report on Investigating P2P Data Leakage.pdf
│   └── Investigating P2P Data Leakage at Beat Step.pptx
├── Code/
│   └── hex.py
```

---

## 📝 Case Summary

**Incident**: Unauthorized sharing of two sensitive audio files:
- `Contraband.mp3` (copyrighted)
- `Sample-1.mp3` (confidential)

**Suspects**: Kamryn Allen (PC seized) and Willis Gibbs

**Objective**: Determine the source, method, and extent of the data breach.

---

## 🔍 Forensic Methodology

### 🧾 Acquisition
- **Disk Imaging**: `Disk_Image_ID-20210327.001`
- **Hash Validation**: `md5deep`, `sha1deep`

### 🔁 Recovery
- Audio and torrent files from unallocated space
- Email artifacts via Mozilla Thunderbird
- Browser history (Microsoft Edge)

### 🔬 Analysis
- Registry analysis with `Regripper`
- Timeline reconstruction using `analyzeMFT`
- Metadata verification using `ExifTool`, `hexedit`, `strings`
- SQLite3 for browser and download activity

### 📢 Presentation
- Structured report documenting all findings
- Chain of custody, evidence tables, screenshots, and conclusions

---

## 🔧 Tools Used

| Tool         | Purpose                                     |
|--------------|---------------------------------------------|
| `md5deep` / `sha1deep` | Verify file integrity                 |
| `Regripper`  | Windows Registry analysis                   |
| `icat` / `fls` | File recovery and inode-based extraction   |
| `sqlite3`    | Browser history and download logs analysis  |
| `Mutt`       | Email artifact recovery                     |
| `strings` / `hexedit` | Binary pattern extraction and inspection |
| `ExifTool`   | Metadata inspection of media files          |
| `analyzeMFT` | Master File Table (MFT) analysis            |

---

## 📂 Python Script

The `Code/hex.py` file is a stub for further forensic automation or binary data parsing. It can be extended to:
- Compare hash values
- Identify file signatures
- Parse MFT records or .torrent files

> 🔧 You can contribute by improving this script for automated hash validation or hex analysis.

---

## 📅 Timeline Highlights

| Date       | Event                                                   |
|------------|----------------------------------------------------------|
| Mar 10     | Kamryn downloaded uTorrent and Thunderbird               |
| Mar 21     | Received `Sample-1.mp3` from Willis                      |
| Mar 27     | Received `Contraband.mp3.torrent` and forwarded files externally |
| Mar 27     | Posted “New Music” thread on **Social Upload** forum     |

---

## 🧩 Key Findings

- Kamryn possessed both files with hash matches to original versions
- Email artifacts confirm Willis sent both files
- Kamryn created `Sample-1.mp3.torrent` locally using uTorrent
- `Contraband.mp3.torrent` was made with qBittorrent (not on her system)
- Kamryn distributed both files to outside parties via email

---

## 🛡️ Recommendations

- Ban unauthorized use of torrent and email clients
- Implement endpoint traffic monitoring
- Conduct periodic digital forensic audits
- Improve access control and employee awareness training

---

## 👩‍💼 Author

**K. Anugna Sai (AP24122050013)**  
*M.Tech Cybersecurity – SRM University, AP*  
*April 2025*

---

## 📄 License

This repository is for academic and educational purposes only.


---

## 📚 Acknowledgements

This investigation was conducted using lab materials and case data adapted from:

[frankwxu/digital-forensics-lab](https://github.com/frankwxu/digital-forensics-lab)  
© Frank Wu — For educational and research purposes
