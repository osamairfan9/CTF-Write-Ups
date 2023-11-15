#!/bin/bash

# URLs
cred_url="https://github.com/osamairfan9/CTF/raw/main/Workshop/credentials.txt"
text_url="https://github.com/osamairfan9/CTF/raw/main/Workshop/text.txt"
pass_url="https://github.com/osamairfan9/CTF/raw/main/Workshop/pass.txt"
dora_url="https://github.com/osamairfan9/CTF/raw/main/Workshop/pass.PNG"
web_url="https://github.com/osamairfan9/CTF/raw/main/Workshop/index.html"
binary_url="https://github.com/osamairfan9/CTF/raw/main/Workshop/binary.jpeg"

# Destinations
dest1="/home/kali/Downloads"
dest2="/home/kali/Pictures"

# Folder 1
folder1="$dest1/ACM"
sudo mkdir -p "$folder1"
sudo chmod 777 "$folder1"

# Subfolder 1
subfolder1="$folder1/Secret"
sudo mkdir -p "$subfolder1"
sudo chmod 777 "$subfolder1"

# Download stuff
sudo curl -L -o "$subfolder1/credentials.txt" "$cred_url"
sudo curl -L -o "$subfolder1/password.PNG" "$dora_url"
sudo curl -L -o "$subfolder1/text.txt" "$text_url"

sudo chmod 777 "$subfolder1/credentials.txt"
sudo chmod 777 "$subfolder1/password.PNG"
sudo chmod 777 "$subfolder1/text.txt"

# Folder 2
folder2="$dest2/Hidden"
sudo mkdir -p "$folder2"
sudo chmod 777 "$folder2"

# Download stuff
sudo curl -L -o "$folder2/pass.txt" "$pass_url"
sudo chmod 777 "$folder2/pass.txt"


