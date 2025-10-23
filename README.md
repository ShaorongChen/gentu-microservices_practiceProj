# 🏛️ Universities Listing Microservice

## 📖 Overview
This microservice provides a REST API for listing and searching universities in the UK.

## 🚀 Features
- Get list of all universities
- Search universities by name

## 🛠️ Setup
1. Clone the repository
2. Install dependencies using `pip install -r requirements.txt`
3. Run the application with `python app.py`

## 📡 API Endpoints
- `GET /colleges` - Get list of all universities
- `GET /colleges/:name` - Search universities by name

## 📦 Docker
To build and run using IBM Cloud CE:
```bash
ibmcloud ce app create --name listing --image us.icr.io/${SN_ICR_NAMESPACE}/listing --registry-secret icr-secret --port 5000 --build-context-dir listing --build-source .
```
Other Command
```bash
#Get Deployed Instances
ibmcloud ce app get --name listing -q
#Update set min. Instances
ibmcloud ce app update --name listing --min 2
```

## 📁 File Structure
- `app.py` - Main application file
- `UK_Universities.json` - University data file
- `Dockerfile` - Docker build configuration

## 🧪 Testing
The service includes tests for API endpoints.

---

# University Websites Microservice

## Overview
This microservice provides a REST API for retrieving university websites based on the name of a university.

## Features
- Retrieve university websites by name
- CORS support for cross-origin requests
- JSON response format

## Project Structure
```
universities/
  └── websites/
      ├── app.py              # Main Flask application
      ├── Dockerfile          # Docker build configuration
      ├── requirements.txt    # Python dependencies
      └── UK_Universities.json # Data file with university information
```

## Setup
1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Run the application:
   ```bash
   python app.py
   ```

3. Access the API at `http://localhost:5000/websites/<name>`

## Docker
To build and run using IBM Cloud CE:
```bash
ibmcloud ce app update --name websites --image us.icr.io/${SN_ICR_NAMESPACE}/websites --registry-secret icr-secret --port 5000 --build-context-dir websites --build-source .
```

Other Command
```bash
#Get Deployed Instances
ibmcloud ce app get --name websites -q
#Update set min. Instances
ibmcloud ce app update --name websites --min 2
```