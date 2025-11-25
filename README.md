# 🚀 Phase X — Splunk Windows Log Ingestion Lab 🔥

In this lab, I ingested Windows event logs into Splunk, verified them, and ran SPL searches to start practicing SOC analysis.

---

# 📂 Create Working Folder
I created a dedicated folder on my system to store all the logs I planned to ingest into Splunk.  

<img width="831" height="197" alt="sIMOQEC" src="https://github.com/user-attachments/assets/e680284e-bbd6-45d6-9ae3-b3361466648a" />

>- 🖥️ File Explorer — for folder creation and organization  
>- 📁 `C:\Users\Jose\Documents\SplunkLogs` — main folder for logs  

---

# 📥 Export Windows Event Logs
I exported all primary Windows logs into my working folder for Splunk ingestion.  

<img width="1274" height="362" alt="2gygHOm" src="https://github.com/user-attachments/assets/7f98985d-5f40-40c5-aac6-eb8008ca377c" />

---

<img width="910" height="137" alt="BjqFA4t" src="https://github.com/user-attachments/assets/46608d69-3d5d-4de3-a606-9ef89b501a8a" />

>- 🗂️ `Security.evtx` — security-related events like logins  
>- 🗂️ `pfirewall.log` — firewall log I already had  

---

# ✅ Confirm Files
I verified that all the exported logs existed in my folder to ensure Splunk would have the correct input.  
>- 💻 PowerShell — used to list folder contents  
>- 🔍 Confirmed presence of: `System.evtx`, `Security.evtx`, `Application.evtx`, `pfirewall.log`  

---

# 🚀 Ingest Logs into Splunk
I uploaded all logs into Splunk, letting it detect sourcetypes and assigning indexes to organize the data.  

<img width="656" height="160" alt="82tZnzF" src="https://github.com/user-attachments/assets/0024ff06-85bf-4bd6-b4bc-7df806f24d89" />

---

>- 🌐 Splunk Web — accessed via browser  
>- ⚙️ Uploaded files from `SplunkLogs` folder  
>- 📝 `.evtx` logs auto-detected as WinEventLog types, `pfirewall.log` as syslog  
>- 🗄️ Assigned index `win_logs` to centralize log storage  

---

# 🔍 Verify Data & Run SPL Searches
I verified that logs were correctly ingested, checked indexes and sourcetypes, and ran SPL queries to validate the data.

### Step 5a — Verify the Index
I confirmed the index existed and reviewed event counts by sourcetype to ensure proper ingestion.  

<img width="1040" height="211" alt="CrtUMUF" src="https://github.com/user-attachments/assets/212fa814-abef-4b0a-86e3-0341f1aa7ebf" />

>- 🗂️ Confirmed `win_logs` index existence  
>- 🔎 Reviewed counts for all sourcetypes  

### Step 5b — Verify Sourcetype
I checked that each log was assigned the correct sourcetype and adjusted my SPL queries if needed.  

<img width="953" height="211" alt="fNHCACl" src="https://github.com/user-attachments/assets/4a94eb27-417e-4ff9-88c1-78e788ea4171" />

>- `.evtx` files detected as WinEventLog:System, WinEventLog:Security, WinEventLog:Application  
>- Firewall log detected as syslog  
>- Adjusted queries for any auto-assigned variations  

### Step 5c — Check the Time Range
I ensured all events were visible by reviewing the time range across all ingested data.  

<img width="790" height="205" alt="t9iRBy6" src="https://github.com/user-attachments/assets/9fc57009-da6b-4e0a-9a4c-9f753380fe96" />

>- ⏰ Set to display all time periods  

### Step 5d — Preview Your Data
I quickly reviewed sample events to confirm ingestion before running more complex searches.  

<img width="877" height="234" alt="MWFXrR3" src="https://github.com/user-attachments/assets/767d071f-20e0-44e2-bbbd-2f5cdc8285ea" />

>- 🔹 Verified first 10 events exist  

### Step 5e — Run Basic Verification Searches
I validated the core log types with SPL queries.  

<img width="670" height="224" alt="godGYvY" src="https://github.com/user-attachments/assets/c1be8b1f-2df0-489f-8ab4-47ca32cc1e9b" />

**Windows Security**  
I checked counts of login events by EventCode and verified successful versus failed logins.  

<img width="877" height="234" alt="MWFXrR3" src="https://github.com/user-attachments/assets/906b5568-95bd-4fd4-a260-d5b92b2aa92c" />

**Windows Firewall**  
I examined firewall logs to see source, destination, and action counts.  

<img width="671" height="218" alt="7DKvMzo" src="https://github.com/user-attachments/assets/38564132-47a0-4133-9a3a-6d0ee940bccb" />

---

# 🛑 Shutdown Docker
I stopped the Splunk container to safely close my lab environment.  

<img width="448" height="122" alt="dcxwCNP" src="https://github.com/user-attachments/assets/93d2c90c-4ab3-4e39-b645-6df1d083edfa" />

>- 🐳 Stopped the `splunk-lab` container  
>- 🔄 Restarted later when resuming practice  
>- ✅ Verified container status to ensure proper shutdown  
