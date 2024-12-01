
# Lamhe: A Basic Web Application for Converting Photos to Videos with Background Audio

**Lamhe** is a web application designed to transform photos into videos by adding background audio. This project was developed as part of the course "Introduction to Software Systems" by **Rohan**, **Himank**, and **Akmal**.

## Key Features
- **Framework:** Built with Flask.
- **Video Processing:** Utilizes the MoviePy module to convert images into video.
- **Database:** Uses PostgreSQL to store user data and provide authentication.
 ## Deployed successfully on render.com
 - * link :https://lamhe-a-web-application.onrender.com
## Installation Guide

### Step 1: Clone the Repository
First, clone the git repository to your local machine:

```bash
git clone <repository-url>
```

### Step 2: Install Required Modules
Navigate to the project directory and install all necessary modules:

```bash
pip install -r requirements.txt
```

### Step 3: Configure the Database Connection

#### For Local Development:
1. Open `app.py`.
2. **Comment out** the section for Render connection:
   ```python
   # db connection for render
    def get_db_connection():
        # Decode the base64 certificate
        cert_decoded = base64.b64decode(os.environ['ROOT_CERT_BASE64'])
        
        # Define the path to save the certificate
        cert_path = '/opt/render/.postgresql/root.crt'
        os.makedirs(os.path.dirname(cert_path), exist_ok=True)
        
        # Write the certificate to the file
        with open(cert_path, 'wb') as cert_file:
            cert_file.write(cert_decoded)
        
    #     # Set up the connection string with the path to the certificate
        conn = psycopg2.connect(
            f"host=jhag21615v-8917.8nk.gcp-asia-southeast1.cockroachlabs.cloud "
            f"port=26257 dbname=defaultdb user=rohan "
            f"password={db_password} sslmode=verify-full "
            f"sslrootcert={cert_path}"
        )
        return conn
   ```

3. **Uncomment** the section for localhost connection:
   ```python
   # db connection for local host
    def get_db_connection():
        # Use f-string to inject the password into the connection string
        conn = psycopg2.connect(
            f"postgresql://rohan:{db_password}@jhag21615v-8917.8nk.gcp-asia-southeast1.cockroachlabs.cloud:26257/lamhe?sslmode=verify-full"
        )
        return conn
   ```

### Step 4: Run the Application
Run the Flask application using:

```bash
python3 app.py
```

### Step 5: Access the Web Application
Open your web browser and navigate to:

```
http://127.0.0.1:5000/
```

---

## Achievement Unlocked 🎉🌟🎊
Congratulations! You have successfully installed and launched the **Lamhe** web application. 🥳 Time to unleash your inner Spielberg and create some epic videos! 🎥📸
```


