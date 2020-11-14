import cv2
import cv2 as cv
import numpy as np
import matplotlib
from pylab import *
from PIL import ImageOps
from PIL import Image
%matplotlib inline
#Le but de la ligne ci-dessus est d'afficher les tracés matplotlib en ligne
import matplotlib.pyplot as plt
import matplotlib.image as mpimg

#image de départ
img = cv2.imread('coins.png',0)

ES = cv2.getStructuringElement(cv2.MORPH_ELLIPSE, (3,3))

erosion = cv2.erode(img,ES,iterations = 1)
dilation = cv2.dilate(img,ES,iterations = 1)
opening = cv2.morphologyEx(img, cv2.MORPH_OPEN, ES, iterations = 2)
closing = cv2.morphologyEx(img, cv2.MORPH_CLOSE, ES, iterations = 2)
gradient = cv2.morphologyEx(img, cv2.MORPH_GRADIENT, ES, iterations = 1)





#cv2.imshow('mon image ',img)
#cv2.imshow('image erodé ',erosion)
#cv2.imshow('image dilaté ',dilation)
#cv2.imshow('ouverture ',opening)
#cv2.imshow('fermeture  ',closing)
#cv2.imshow('la différence entre la dilatation et l’érosion ',gradient)
cv2.waitKey(0)
cv2.destroyAllWindows()


