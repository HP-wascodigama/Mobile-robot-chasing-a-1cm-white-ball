# Mobile-robot-chasing-a-1cm-white-ball
Using ROS, Gazebo and Rviz chasing 1cm white ball with wheeled mobile robot carring with cmera and laidar sensors

#initial setup
1. install ros-noetic in ubuntu
2. creat catkin workspace and source dirctory
3. $cd ~/catkin_ws
4. $catkin_make
5. $source devel/setup.bash
6. $cd src
7. $git clone https://github.com/HP-wascodigama/Mobile-robot-chasing-a-1cm-white-ball/tree/main/ball_chaser
8. $git clone https://github.com/HP-wascodigama/Mobile-robot-chasing-a-1cm-white-ball/tree/main/my_robot
9. $cd ..
10. for white boll you need to creat a white ball model using gazebo editing mode and save it as my_ball in your workspace directory. Ball radious 0.1 and set all colour visualizing option value to 1.   
11. $catkin_make
12. $source devel/setup.bash
13. $roslaunch my_robot world.launch
14. open new terminal
15. $source devel/setup.bash
16. $roslaunch ball_chaser ball_chaser.launch
17. open new terminal
18. $rosrun rqt_image_view rqt_image_view
19. In Rviz go in display section
20. 1. select globle option and change fixed fram from 'map' -> 'odom'
21. 2. select Add tab and select camera and choose image_topic
22. 3. Add robot model
23. 4. Add LaserScan option and then choose Topic -> /scan

Now you would be able to find my_ball in insert option of gazebo, select it and put in workframe. Robot will chase when it found white ball in it's camera range.
