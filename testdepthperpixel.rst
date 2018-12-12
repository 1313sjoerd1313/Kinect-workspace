#!/usr/bin/env python
from __future__ import print_function

import roslib
#roslib.load_manifest('my_package')
import sys
import rospy
import cv2
from std_msgs.msg import String
from sensor_msgs.msg import Image
from cv_bridge import CvBridge, CvBridgeError


def get_distance (img):
	bridge=CvBridge()
	cv_image = bridge.imgmsg_to_cv2(img,"32FC1")
	print cv_image[10,10]

rospy.Subscriber('/camera/depth/image_raw',Image,get_distance)

