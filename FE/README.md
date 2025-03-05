# GroceryAppFE DOCKERFILE🚀  

## 📌 Getting Started  
Follow the steps to create and dockerfile  

### ✅ Prerequisites  

Clone the repository
make changes into REACT_APP_API_URL

When building a React app using a Dockerfile, updating REACT_APP_API_URL (or any other environment variable prefixed with REACT_APP_) is necessary because React applications are static single-page applications (SPA). This means that environment variables are baked into the build at compile time and cannot be changed later.

**1st method (preffered)**

in the dockerfile RUN sed -i's|REACT_APP_API_URL=http://35.192.28.119:5000|REACT_APP_API_URL=http://**43.204.215.101**:5000|' .env
copy your backend ip into it, in this bold highlighted command and save the file.

create the directory to run the build directory files and packages (mkdir -p /var/www/grocery-app manually)

Create a file manually for nginx configuration in the /FE directory - nginx.conf and paste 




server {

    listen 80;
    
    server_name your_domain_or_ip;   #- Replace  `your_domain_or_ip`  with your server public IP of frontend
    
    root /var/www/grocery-app;
    
    index index.html;
    
    location / {
    
        try_files $uri /index.html;
    }
}

OR 

**2nd method (optional)** (go inside the directory /FE
after that there is hidden file .env (view the file by ls -a) 
made changes into it by vim .env and paste your backend ip**
REACT_APP_API_URL=http://webserverpublicIP:5000 ) and remove the REACT_APP_URL command line from dockerfile, as you already make directly changes into the .env


**NOTE** - After making changes into nginx conf file and creating directory in /var. Then only build the docker file.
