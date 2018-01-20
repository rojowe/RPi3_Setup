# RPi3_Setup
<p>
  These basic first steps will get you up and running with a headless setup. 
  <ul>
    <li>Static IP</li>
    <li>SSH</li>
    <li>VNC</li>
    <li>Samba</li>
  </ul>
</p>

<p>
  Open Terminal:
  <ul>
    <li>sudo apt update</li>
    <li>sudo apt upgrade</li>
    <li>sudo apt dist-upgrade</li>
    <li>sudo raspi-config</li>
  </ul>
</p>

<p>
  <ul>
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
  Open Terminal:
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
  SSH Into RPi
  <ul>
    <li>sudo apt install ufw</li>
    <li>sudo ufw allow 22</li>
    <li>sudo ufw allow 5901</li>
    <li>sudo ufw enable</li>
  </ul>
</p>

<p>
  <ul>
    <li>sudo apt install fail2ban</li> 
    <li>sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local</li>
  </ul>
</p>

<p>
  <ul>
    <li>sudo apt install tightvncserver 
    <li>sudo nano /etc/rc.local</li>
        <ul>
          <li>below "fi"</li>
          <li>#start VNCserver @ boot</li>
          <li>su - pi -c '/usr/bin/tightvncserver :1'</li>
        </ul>
    <li>sudo reboot</li>
  </ul>
</p>

<p>
  <ul>
    <li>sudo apt install samba</li> 
    <li>sudo ufw allow (137, 138, 139, 445)</li>
    <li>sudo mkdir -m 1777 /home/pi/Shared</li>
    <li>sudo nano /etc/samba/smb.conf</li>
     <ul>
       <li>[share]</li>
       <li>Comment = Pi shared folder<\n>
       <li>Path = /home/pi/Shared<\n>
       <li>Browseable = yes<\n>
       <li>Writeable = Yes<\n>
       <li>only guest = no<\n>
       <li>create mask = 0777<\n>
       <li>directory mask = 0777<\n>
       <li>Public = yes<\n>
       <li>Guest ok = yes<\n>
     </ul>
    <li>sudo reboot</li>
  </ul>
</p>
