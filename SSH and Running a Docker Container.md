# SSH
ssh <username>@192.168.55.1

# Data Folder
mkdir -p ~/nvdli-data

# Run the docker container
sudo docker run --runtime nvidia -it --rm --network host \
    --volume ~/nvdli-data:/nvdli-nano/data \
    --device /dev/video0 \
    nvcr.io/nvidia/dli/dli-nano-ai:<tag>
                    

# create a reusable script
echo "sudo docker run --runtime nvidia -it --rm --network host \
    --volume ~/nvdli-data:/nvdli-nano/data \
    --device /dev/video0 \
    nvcr.io/nvidia/dli/dli-nano-ai:v2.0.2-r32.7.1" > docker_dli_run.sh

# make the script executable
chmod +x docker_dli_run.sh

# run the script
./docker_dli_run.sh


# Logging into the JupyterLab server

Open the following link address : 192.168.55.1:8888
The JupyterLab server running on the Jetson Nano will open up with a login prompt the first time.
Enter the password: dlinano