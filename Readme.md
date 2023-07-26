## Commands to Run a Blockchain (Ncog Earth Chain)

```bash
# Update package lists and upgrade installed packages
apt upgrade -y

# Install software-properties-common
apt install -y software-properties-common

# Add the Go programming language repository
add-apt-repository -y ppa:longsleep/golang-backports

# Update package lists after adding the repository
apt update

# Install Golang
apt install -y golang-go

# Install zip and unzip tools
apt install -y zip unzip

# Install make
apt install -y make

# Install git
apt install -y git

# Automatically remove unnecessary packages
apt autoremove -y

# Clean the package cache
apt autoclean -y

# Clone the Ncog Earth Chain repository
git clone https://github.com/Ncog-Earth-Chain/go-ncogearthchain

# Navigate to the cloned repository directory
cd go-ncogearthchain

# Build the Ncog Earth Chain blockchain
make ncogearthchain

# Move to the "build" directory
cd build

# Clone the testnet repository inside the "build" directory
git clone https://github.com/Ncog-Earth-Chain/testnet

# Move to the "testnet" directory
cd testnet

# Copy the "testnet.g" file one level up (to the "build" directory)
cp ./testnet.g ../.

# Generate the config file using the ncogearthchain tool
./ncogearthchain dumpconfig > config.toml

# Now you can run the blockchain as:
./ncogearthchain --genesis testnet.g --config config.toml
