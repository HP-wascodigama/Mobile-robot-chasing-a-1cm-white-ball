# Mobile-robot-chasing-a-1cm-white-ball
Using ROS, Gazebo and Rviz chasing 1cm white ball with wheeled mobile robot carring with cmera and laidar sensors

#initial setup
1. install ros-noetic in ubuntu
2. creat catkin workspace and source dirctory
3. $cd ~/catkin_ws
4. $catkin_make
5. $source devel/setup.bash
6. $cd src
7. you may clone or download zip file and extract it in catkin workspace, src directory 
8. $git clone https://github.com/HP-wascodigama/Mobile-robot-chasing-a-1cm-white-ball/tree/main/ball_chaser
9. $git clone https://github.com/HP-wascodigama/Mobile-robot-chasing-a-1cm-white-ball/tree/main/my_robot
10. $cd ..
11. for white boll you need to creat a white ball model using gazebo editing mode and save it as my_ball in your workspace directory. Ball radious 0.1 and set all colour visualizing option value to 1.   
12. $catkin_make
13. $source devel/setup.bash
14. $roslaunch my_robot world.launch
15. open new terminal
16. $source devel/setup.bash
17. $roslaunch ball_chaser ball_chaser.launch
18. open new terminal
19. $rosrun rqt_image_view rqt_image_view
20. In Rviz go in display section
21. 1. select globle option and change fixed fram from 'map' -> 'odom'
22. 2. select Add tab and select camera and choose image_topic
23. 3. Add robot model
24. 4. Add LaserScan option and then choose Topic -> /scan

Now you would be able to find my_ball in insert option of gazebo, select it and put in workframe. Robot will chase when it found white ball in it's camera range.
