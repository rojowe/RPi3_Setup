<h3>openHAB2 Setup</h3>

<b>Features</b>
- Home Automation Server
- MQTT Server
- 

Installation Instructions

//Step 1
wget -qO - 'https://bintray.com/user/downloadSubjectPublicKey?username=openhab' | sudo apt-key add -

//Step 2
sudo apt-get install apt-transport-https

//Step 3
echo 'deb https://dl.bintray.com/openhab/apt-repo2 stable main' | sudo tee /etc/apt/sources.list.d/openhab2.list

//Step 4
sudo apt-get update

//Step 5
sudo apt-get install openhab2

//Step 6
sudo apt-get install openhab2-addons
