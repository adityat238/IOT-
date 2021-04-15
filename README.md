# IOT-
iot project to turn on lights and devices from google assistant
import time 
#import Rpi.GPIO as GPIO
from Adafruit_IO import Client
ADAFRUIT_IO_USERNAME = "adityatakiar"
ADAFRUIT_IO_KEY = "aio_PQqh242GSNb0FUa3wjf2uF63ct04"
######################################################
aio = Client(ADAFRUIT_IO_USERNAME,ADAFRUIT_IO_KEY)
xlight = aio.feeds('light123')
while True:
    mylightdata = aio.receive(xlight.key)
    print('light', mylightdata.value)
    a=mylightdata.values
    a=int(a)
    if a==1:
        print ("light on")
    else :
        print("light off")
