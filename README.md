# Monitor Fabric Activity with Microsoft Fabric

This repository contains the steps and screenshots of a hands-on project where we used Microsoft Fabric to create, monitor, and customize activity tracking through the Monitoring Hub.

## 🧰 Prerequisites
- Access to a Microsoft Fabric-enabled tenant (Trial, Premium, or Fabric capacity)
- Basic familiarity with dataflows, Lakehouse, and notebooks

---

## ✅ Step-by-Step Summary

### 1. Create a Workspace
- Navigate to https://app.fabric.microsoft.com
- Create a new workspace with a name of your choice
- Make sure it uses a Fabric capacity license (Trial, Premium, or Fabric)

---

### 2. Create a Lakehouse
- In the workspace, go to **Create > Lakehouse**
- Name it uniquely
- After a minute, a new, empty Lakehouse will be available

---

### 3. Create and Monitor a Dataflow (Gen2)
- From your Lakehouse home page, choose **Get Data > New Dataflow Gen2**
- Name it `Get Product Data`
- Use **Import from a CSV** and enter:  
  `https://raw.githubusercontent.com/MicrosoftLearning/dp-data/main/products.csv`  
  with **anonymous authentication**
- Preview the data and publish the dataflow
- Go to **Monitor** to track the dataflow status
- Wait until the run status becomes **Succeeded**
- Open your Lakehouse > Tables > confirm the `products` table was created

---

### 4. Create and Monitor a Spark Notebook
- Go to **Create > Notebook**
- Rename it to `Query Products`
- From the Explorer pane, choose **Add data items > Existing data sources**
- Add your Lakehouse and expand to the `products` table
- Use **Load data > Spark**
- Run all cells with `▶ Run all`
- After it completes, stop the Spark session (`◻`)
- Monitor the activity in the Monitoring Hub

---

### 5. View Run History for Dataflows
- Go back to your workspace, re-run the dataflow using **↻ Refresh now**
- Go to **Monitor**, find the `Get Product Data` item
- Click `... > Historical runs`
- Select a run and choose `View detail` to inspect the execution metadata

---

### 6. Customize Monitoring Hub View
- In the Monitoring Hub, apply these filters:
  - **Status:** Succeeded
  - **Item type:** Dataflow Gen2
- Open **Column Options** and include:
  - Activity name, Status, Item type, Start time, End time, Duration,
    Submitted by, Location, Refresh type
- Use horizontal scroll if needed to see all columns

---

## 📁 Folder Structure
