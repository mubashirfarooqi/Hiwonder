# Hiwonder
Hiwonder Mentor Pi A1 Ackerman Chassis


SLAM Mapping Tutorial - I wouldn't recommend Hiwonder documentation since it can be confusing

1. Download Workstation Pro 17 (do not download 16)
2. Fix Vmnetbriges.dll error by finding the file/path in the VMWare folder - critical error to fix - it's for the network bridge adapter in Workstation (if you don't have any errors, keep going then, but I have heard downloading Workstation 17.5 or later causes this)
3. Download Hiwonder Virtual Machine in the Appendix under the Mapping and Navigation folder
4. Turn on the Hiwonder Robot
5. Connect your laptop to the Hiwonder hotspot -> it starts with "HW"
6. Log in through VNC. Input IP address as follows: 192.168.149.1.
7. Username: pi, Password: raspberrypi
8. You should be logged in through VNC
9. Through VNC, put the robot in LAN mode by connecting the robot to your home WIFI
10. Insert the following code in VNC LxTerminal: vim hiwonder-toolbox/wifi_conf.py
11. Insert your home WIFI username and password under STA username and password
12. After exiting, insert the following code: sudo systemct1 restart wifi.service
13. The Hiwonder robot should now be connected to your WIFI
14. You will lose access to VNC
15. Find the new IP address for the robot so you can use VNC again
16. Personally, I connected a micro USB to HDMI from the Raspberry Pi to a monitor
17. Connect a Mouse and Keyboard to the Raspberry Pi as well
18. Additionally, you can find the IP address from the WonderPi app when connecting your phone, but I ran into errors
19. The new IP address should be found at the top right of the screen by the WIFI logo
21. Connect to VNC again with the new IP address
22. Disconnect HDMI, mouse, and keyboard since you won't need them anymore
23. Username and Password are the same for logging through VNC again (STEP 7)
24. Open Workstation Pro 17 and click Open Virtual Machine, and click on HiWonder_ros2_humble in your downloaded files
25. Open the virtual machine -> everything is set up for you so you don't have to edit anything
26. Run the following code in VNC to start SLAM:
27.  ~/.stop_ros.sh
28. ros2 launch slam slam.launch.py
29. Run the following code in your Virtual Machine: ros2 launch slam rviz_slam.launch.py
30. Run the following code in VNC by opening another Terminator (do not close the current one): ros2 launch peripherals teleop_key_control.launch.py
31. You can now move the robot with your keyboard


