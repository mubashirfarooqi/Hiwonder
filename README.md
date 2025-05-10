# Hiwonder
Hiwonder Mentor Pi A1 Ackerman Chassis


SLAM Mapping Tutorial - I wouldn't recommend Hiwonder documentation since it can be confusing

1. Download Workstation Pro 17 (do not download 16)
2. Fix Vmnetbriges.dll error by finding the file/path in the VMWare folder - critical error to fix - it's for the network bridge adapter in Workstation (if you dont have any error, keep going then but I have heard downloading workstation 17.5 or later causes this)
3. Download Hiwonder Virtual Machine in the Appendix under the Mapping and Navigation folder
4. Through VNC, put the robot in LAN mode by connecting the robot to your home WIFI
5. Insert the following code in VNC LxTerminal: vim hiwonder-toolbox/wifi_conf.py
6. insert your home WIFI username and password under STA username and password
7. After exiting, insert the following code: sudo systemct1 restart wifi.service
8. Robot should be connected to your WIFI
9. You will lose access to VNC
10. Find the new IP address for the robot so you can use VNC again
11. Personally, I connected a micro USB to HDMI from the Raspberry Pi to a monitor
12. Connect Mouse and Keyboard into Raspberry Pi as well
13. Additionally, you can find IP address from the WonderPi app when connecting your phone, but I ran into errors
14. New IP address found at top right of screen
15. Connect to VNC again with new IP address
16. Username and Password are the same
17. Run the following code in VNC to start SLAM: ~/.stop_ros.sh -> ros2 launch slam slam.launch.py
18. Run the following code in your Virtual Machine (downloaded from Hiwonder google drive folder)-> ros2 launch slam rviz_slam.launch.py
19. Run another command in VNC by opening another terminator (do not close the current one) -> ros2 launch peripherals teleop_key_control.launch.py

