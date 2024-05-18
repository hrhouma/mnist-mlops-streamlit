```sh
su
#ou sudo -s
pwd
git clone https://github.com/hrhouma/install-docker.git
cd /install-docker/
chmod +x install-docker.sh
./install-docker.sh
#ou sh install-docker.sh
docker version
docker compose version
```

### Solution 2: Use Python Virtual Environment for Docker Compose

1. **Install `pip` if it's not already installed:**
   ```sh
   sudo apt-get update
   sudo apt-get install -y python3-pip
   ```

2. **Create a Python virtual environment and activate it:**
   ```sh
   sudo apt-get install -y python3-venv
   python3 -m venv docker-compose-venv
   source docker-compose-venv/bin/activate
   ```

3. **Install Docker Compose within the virtual environment:**
   ```sh
   pip install docker-compose
   ```

4. **Use Docker Compose from the virtual environment:**
   ```sh
   docker-compose --version
   ```

### Additional Steps to Execute Your Project

1. **Navigate to your project directory:**
   ```sh
   cd /home/ubuntu/mnist-mlops-learning
   ```

2. **Build the Docker images:**
   ```sh
   docker-compose build
   ```

3. **Start the services:**
   ```sh
   docker-compose up -d
   ```

4. **Check the logs to ensure everything is running correctly:**
   ```sh
   docker-compose logs
   ```

By following these steps, you should be able to build and run your Docker containers on your EC2 instance without encountering the `ssl_version` error.

---------
# Fastapi + MLflow + streamlit

Setup env. I hope I covered all.
```bash
pip install -r requirements.txt
```
# Start app
Go in the root dir and run these

Streamlit
```bash
streamlit run frontend/streamlit_main.py
```

FastAPI 
```
uvicorn backend.main:app
```

MLflow UI
```bash
mlflow ui --backend-store-uri sqlite:///db/bakckend.db
```

## Docker
- Mlflow: http://localhost:5000
- FastApi: http://localhost:8000/docs
- Streamlit: http://localhost:8501/

```bash
docker-compose build
docker-compose up
```

# Architecture
![image](resources/arch.png)

# UI 
![image](resources/train_pic.png)
![image](resources/pred_pic.png)


## TODO
- [x] Dockerize
- [ ] Testing
- [ ] Maybe add celery instead of that background task? (Needs extra configs though)

