# Project Description

Creating detailed 3D environments for games / experiences in virtual reality is a labor intensive process, especially when trying to accurately model real life areas. Using 360-degree cameras with some sort of distance gauge is a solution, but this setup is clunky, hard to keep stable and can bring unwanted attention from nearby people, ruining the map. By packaging the sensors discretely in a backpack, only having small holes / one-way tints cut out for cameras and other sensors, you can create discrete real-time modeling. * this would require some sort of lidar setup, covering front and back. This setup will have an appendage that extends out front as well (wires hidden under clothes). TBD: location to attach front appendage? belt buckle? backpack shoulder strap? Applications: - creating virtual reality experiences - creating 3d tours of places - reliving places you visit - can be used for advertising real life experiences - potential safety related applications: using computer vision to analyze all around you in real time

# Bill of Materials

# Internal Frame CAD 

# Software 

# Construction Process

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Journal: 

#Initial Render
<img width="1667" height="695" alt="image" src="https://github.com/user-attachments/assets/99518934-c55e-40c5-940a-fb22883ea43c" />

Thoughts: 
for measuring distances, I decided that LiDAR will be the most efficient.
I skimmed a few research papers about SLAM (Simultaneous Localization and Mapping) and found that along LiDAR, I should also have an IMU and a camera system.

My main concern currently is the packaging + discreteness of the system.

My current solution to this is a 3d printed frame that is screwed on to the fabric of the backpack in multiple points to hold it steady.

I also want some sort of tinted acrylic that the LiDAR lasers can pass through. The cameras will have holes that they poke out of (attached to the frame as well)


# Walking Algorithm
<img width="1731" height="578" alt="image" src="https://github.com/user-attachments/assets/709849b9-bcf1-4674-8f2f-7c19598ea4b0" />

A major consideration is whether the system needs frontal and rear vision.

I analyzed a few different scenarios and found that having frontal vision is redundant for most scenarios.

For most enclosed spaces, mapping just behind you requires minimal more walking.

This means that the algorithm for walking in enclosed spaces should be to finish the path and then turn around and walk enough for the camera's pan to cover the edge of the desired space.

For open spaces, the process is similar and depends on how open the space is (might need to trace the perimeter of the 'end' of the path region. But since we don't have to account for objects past the LiDAR's range, open spaces just require a walk around the (perimeter - the range) * of the camera + LiDAR system..


# Internal Frame
<img width="872" height="642" alt="image" src="https://github.com/user-attachments/assets/b80d6c4a-376b-44fc-9dfb-f54ccde4c1a4" />


I need to make sure the structure of the system stays constant and as still as possible in the backpack. My idea is to create a 3d printed frame that screws onto the backpacks fabric and stays tight.
I want all the measurement units to connect onto the same rigid body so that they are more consistent to each other in measurements => a more consistent SLAM performance.

I will also have to plan where to keep the electronics for the system. Since I am using a backpack, I may be able to hook up my PC to the components, which would be great for the processing power 

required for the real-time algorithms. If I can't plan this spatially / the frame would press against my computer screen, then I plan to use a raspberry pi to manage storing all the measurements, which I would then use a custom software program to compute and then render into a 3d model file.

# References


