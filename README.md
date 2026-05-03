# Windows Artifact Analysis & Timeline Reconstruction (DFIR Project)

## 📌 Overview
This project focuses on forensic analysis of Windows system artifacts to reconstruct user activity. The investigation covers Event Logs, Prefetch files, Thumbcache, Browser Cache, and Recycle Bin data.

---

## 🛠 Tools Used
- EvtxECmd
- PECmd
- Autopsy
- MFTExplorer
- PowerShell
- Microsoft Excel

---

## 🔍 Methodology

### 1. Event Log Analysis
- Collected Security.evtx from system directory
- Preserved integrity by working on a copied file
- Generated SHA256 hash using CertUtil
- Parsed logs into CSV using EvtxECmd
- Filtered key Event IDs (4624, 4672) for logon and privilege activity

### 2. Prefetch Analysis
- Acquired Prefetch files from C:\Windows\Prefetch
- Parsed using PECmd
- Identified executed applications and timestamps

### 3. Cache & Thumbcache Analysis
- Extracted thumbcache database files
- Recovered thumbnail images using thumbcacheviewer
- Analyzed browser cache data for browsing activity

### 4. Recycle Bin Analysis
- Identified deleted files and original paths
- Extracted deletion timestamps
- Recovered evidence of removed files

### 5. Cross-Artifact Correlation
- Correlated Event Logs, Prefetch, Thumbcache, and Recycle Bin
- Built a unified timeline of user activity
- Validated findings across multiple independent sources

---

## 📊 Key Findings
- User logon activity successfully identified from event logs
- Execution of forensic tools confirmed via Prefetch data
- Deleted files recovered through Recycle Bin analysis
- Thumbnail artifacts persisted even after file deletion
- Cross-artifact correlation improved confidence in findings

---

## 📁 Project Structure
