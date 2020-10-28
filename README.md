<h2>RPi3 Clean Install Setup</h2>
<p>
  These basic first steps will get you up and running with a headless setup. 
  <ul>
    <li>Static IP</li>
    <li>SSH</li>
    <li>VNC</li>
    <li>UFW Firewall</li>
  </ul>
</p>

<p>
<h3>Update & Upgrade System & Applications</h3>
<ul>
   <li>sudo apt update</li>
   <li>sudo apt upgrade</li>
   <li>sudo apt dist-upgrade</li>
   <li>sudo raspi-config</li>
   <li>Change Password</li>
   <li>Change Network Options - Hostname</li>
   <li>Change Boot Options - Desktop Autologin</li>
   <li>Change Timezone</li> 
   <li>Enable SSH Interface</li>
   <li>Enable VNC Interface</li>
   <li>Advanced Options - Expand Filesystem</li>
   <li>Finish & Reboot</li>
</ul>
</p>

<p>
<h3>Set Static IP</h3>
<ul>
   <li>sudo nano /etc/dhcpcd.conf</li>
   <li>static eth0</li>
   <li>static ip_address=192.168.x.xxx</li>
   <li>static router=192.168.x.1</li>
   <li>static DNS=192.168.x.1 8.8.8.8</li>
   <li>sudo reboot</li>
</ul>
</p>

<p>
<h3>Install firewall UFW</h3>
<ul>
   <li>sudo apt install ufw</li>
   <li>sudo ufw allow 22</li>
   <li>sudo ufw allow 5900</li>
   <li>sudo ufw enable</li>
   <li>sudo apt install fail2ban</li> 
   <li>sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local</li>
</ul>
</p>
