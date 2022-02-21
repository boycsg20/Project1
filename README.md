# Project1
Here will include all our videos, images, and process of completing the project. We began with our problem. Kyle wanted to be notified whenever his front door detached motion. To do this we needed a SIM 900A (or any other) GSM Module with SIM inserted which sends text messages and calls, however we did not have access to this GSM module, so we opted for a I2C LCD which just displays messages. Then we needed to find a sensor. We tried a PIR sensor, but it was not working properly so we switched our sensor to an ultrasonic sensor. Here we tried many methods first in our code to try and make it work such as implementing if and while loops. Since on the plot graph, the sensor was displaying 0s and 1s rapidly, we also attempting to calulate the average value it was displaying over a period of time and work with the data that way, but it still failed to give a clear answer as to whether it was sensing movement or not. With the ultrasonic sensor we could tell the distance of an object and therefore could code when the LCD could turn on. This sensor worked much better in giving us the information we wanted, if someone was there or not. Since we only wanted it when someone was close to the sensor to send a message to whoever was opening the door. However, if we were to code it for our original issue, the distance of detection would be larger as to notify the homeowner for any movement outside. Finally to add a bit of flair, we included a RTC module that tells the time. Our final project is a working prototype that displays a message “Welcome home” when an object is detached within 50 inches of the sensor, just enough to be triggered when the door is opened right in front of it. Our methodology took a lot of trial and error with the modules and the code. Firstly, we learned how to work each module individually as well as figure out how to code them by themselves. This was helpful because when we couldn’t get the PIR sensor to work, we knew it was a problem with the sensor and not the LCD display. Then we combined the ultrasonic sensor and the LCD display and their code as well. We had to tweak the code slightly, but all in all the combination process went smoothly. Finally, implementing the RTC module was a little more difficult as it kept having variables defined out of the scope and a lot of data went into setting up the correct time of the module. Wiring it into the prototype was not physically challenging, but more difficult software wise. All in all ,we tried our project in piece before putting it all together and went through a lot of trial and error processes with our code before our final result. 


https://user-images.githubusercontent.com/90404125/154889580-a0416ab9-6658-4aa9-be5b-12309fad7f2f.mov

[projectonepic1.pdf](https://github.com/boycsg20/Project1/files/8106210/projectonepic1.pdf)

[porjectonepic2.pdf](https://github.com/boycsg20/Project1/files/8106211/porjectonepic2.pdf)

[Project1code.pdf](https://github.com/boycsg20/Project1/files/8111582/Project1code.pdf)





<img width="714" alt="prototype_sketch_1" src="https://user-images.githubusercontent.com/90404125/155014353-50d42bf4-6b17-4693-8497-c8bb86140062.png">





<img width="718" alt="prototype_sketch_2" src="https://user-images.githubusercontent.com/90404125/155014366-543d3bf6-ff02-410b-9de5-4b2704c72289.png">









![image](https://user-images.githubusercontent.com/90404125/155015710-fe40ce7e-3fae-4b64-bacb-b7a35508b597.png)

