# Esp32
CONTROLLING LED LIGHTS USING ESP32 WITH AWS WEB-SERVER

A PROJECT REPORT
Submitted by
RANABIR DAS
AKASH KUMAR
PRIYANKA SAHA
RISHAV KUMAR
ARUNIMA DAS
ARPAN BHATTACHARYA
DEBAPRASAD ROY

In partial fullfilment for the award of the degree of
B. TECH
IN
ELECTRICAL ENGINEERING
At

DECLARATION
                 We hereby declare that the project work being presented in this report entitled “CONTROLLING LED LIGHTS USING ESP32 WEB-SERVER” submitted in the department of Electrical Engineering, Future Institute of Engineering and Management, West Bengal is the work carried out by group members under the guidance of Dr. Pradipta Kumar Banarjee, Professor, Department of Electrical Engineering, Future Institute of Engineering and Management.
                                                                                    														 RANABIR DAS
                                 AKASH KUMAR
RISHAV KUMAR
PRIYANKA SAHA
ARUNIMA DAS
DEBAPRASAD ROY
ARPAN BHATTACHARYA  
B.TECH 7th Semester                                                           Department of Electrical Engineering                                 Future Institute of Engineering and Management                      Kolkata-700150
Date:


ACKNOWLEDGEMENT
                                 
           We would like to express our special thanks of gratitude to our teacher Dr. Pradipta Kumar Banarjee who gave us the opportunity to do this wonderful project on the topic “ CONTROLLING LED LIGHTS USING ESP32 WEB-SERVER” which also helped us in doing a lot of Research and we came to know about so many things. We are really thanks to them. 
 										
AKASH KUMAR
RANABIR DAS
RISHAV KUMAR
PRIYANKA SAHA
ARUNIMA DAS
DEBAPRASAD ROY
ARPAN BHATTACHARYA
B.TECH, 7TH Semester                                                                Department of Electrical Engineering                                                Future Institute of Engineering and Management                       Kolkata-700150
Date:



INDEX OF THE REPORT:
    • Abstract
    • Introduction
    • Popular works in this field by the experts
    • System design approach
    1. System Architecture
    2. Hardware Design
    3. Software Design
    I. Software Architecture
    • Internal system evaluation and discussion
    1. Making of the website
    2. The final outcomes
    3. The final output after adding designs 
    • Conclusion
    • Recommendation Of Improvement
    • References

-----------------




ABSTRACT                                          
The IOT plays an important role in now a days life whether it is in corporate or daily household. To have a security in the house or in the corporate office, the occupants of the house will always have a security door which is manually operated by a human being but if an IOT device is attached and programmed with the door it will be more helpful and affordable to control the first line of defence of a residence or a office from anywhere in the world. We proposed an application which can be accessed from anywhere in the world via an globally controlled web-server and can be modified in further future for more featured security devices. The HTTP(Hyper Text Transfer Protocol) website helps us to connect and control the LED’s from far away from the origin. In this one we just proposed an approach or Prototype by which we can observe and experience the benefits of an IOT which successfully integrated with Amazon Web Server.












Keywords: Home automation, Internet Of Things, AWS, Web-Server, Cloud.


Introduction                                               
A security system can work manually until the IoT comes into the stage. The occupants can be informed by the network of the device at that instance when the security can be sabotaged.
Internet Of Things (IoT) is a structure in which objects and people are provided with exclusive identity and the ability to relocate data over a network without requiring two-way handshaking between human-to-human i.e. source to destination or human-to-computer interaction. IoT utilizes the ability of sensors such as fingerprint sensors, temperature sensors and humidity sensors etc. IoT also utilizes the capabilities of tools such as micro controllers that can control other devices, an led can blink with the help micro controller which can be created by a sever-end request, an alarm that can ring or stop ringing according to the input received, an MOSFET is a transistor which can be in the form of an automatic switch.
MQTT (Message Queue Telemetry Transport) protocol is widely used for network communication used for network communication protocol in IoT. It enables a publish/subscribe mechanism. A receiver device can connect one time to the server to subscribe for a specific topic. Then, whenever there is a message generated for a specific topic, the message will be sent to the receiver. In comparison, when using HTTP, a device (client) which would like to receive a message, needs to request periodically to a server whether there is a message or not. The IoT can modified for various purposes in further research by which it can be controlled by a client-side website remotely via a smart phone through cloud.    




Keywords: MQTT, IoT, remotely, cloud, HTTP, MosFET.

Popular works in this field by the experts                     
In 1990’s John Romkey connected a toaster to the internet for the very first time with a TCP/IP protocol. One year later, University of Cambridge scientists came up with the idea to use the first web camera prototype to monitor the amount of coffee available in their local computer lab’s coffee pot. They programmed the webcam to take pictures of the coffee pot three times per minute, then send the images to local computers, thus allowing everyone to see if there was coffee available.
At the beginning of the 21st century, the term “internet of things” came into widespread use by the media, with outlets like The Guardian, Forbes, and the Boston Globe making mention of it. The very first International Conference on the Internet Of Things held in Switzerland in 2008, where participants from 23 countries discussed RFID, short-range wireless communications, and sensor networks.
The IoT boom was supported by its addition to the Gartner Hype Cycle for emerging technologies in 2011.
In the same year, IPv6- a network layer protocol that is central to IoT was launched publicly.
As of today, IoT platforms maintain a strong hold on their position among the top trends in this year’s Gartner Hype cycle, along with virtual assistants, connected homes, and level 4-self driving cars. The technology will reach it’s plateau of productivity in 5-10 years. 
IoT will become more industry-specific in near future, IoT manufactures will focus on designing solutions for particular industries and industry segments rather than for general needs.
There is a growing demand for specific use cases that help to resolve industry-specific challenges.
New areas are also appearing at the intersections between interconnected technologies and various industries;
    1. Internet of medical things.
    2. Industrial internet of things.
    3. Automotive internet of things.
    4. Smart cities and smart buildings.

Keywords: RFID, Hype Cycle, IPv6, network layer.
              
System Design Approach
The system is implemented using Micro controller ESP32, Arduino programming language and an Android-based mobile application. The micro controller ESP32 is used to integrate all the electronic device in one environment. ESP32 is used because ESP32 has two cores, one core to run Wi-Fi functions and one core to execute uploaded programs. ESP32 also has a Wi-Fi and blue-tooth module, and 36 GPIO. ESP32 has a fairly large memory, and it uses low power also has an internal touch sensor making it suitable for use in door security system development projects. In this section we are going to discuss the system design approach for the proposal of flexible web-server based IoT device.
    1. System Architecture          
   The communication between The ESP32 micro-controller and the AWS web server through MQTT protocol system and SSL encryption. The system design in figure 1 has shown below with brief description; 









FIGURE 1
 	Part 1 is the Internet or we can call it as MQTT Broker. AWS itself is a company that provides MQTT Broker service over the internet so that it can be accessed using the internet. MQTT Broker is in charge of receiving all messages sent to MQTT Broker and delivering messages received to clients who subscribe to certain topics. 
Part 2 is the representation of Publisher & Subscriber (DEVICE) like a smartphone or desktop. In this design the device is the smartphone where we used a website to send instructions in the form of command to MQTT Broker on certain topics which will later be published on clients that subscribe to certain topics, namely micro-controller and MQTT Listener. The device also works as a subscriber where the device will receive some sort of messages according to the topic subscribed by the MQTT broker.
Part 3 is a representation of publisher & subscriber (Micro-Controller)/IoT device. Micro-Controller is a mini computer that is dedicated to run a specific program. In this Section, the micro-controller is responsible for sending messages to MQTT Broker. The ESP32 also functions as a subscriber where the micro-controller will receive a message according to that topic which being subscribed.
Part 4 is the output portion where we fetch all of the requests from the web-server and shows the messages into a digital format on the website. Basically, this part consists of the devices which users are using for their work purposes. So, the user can access the data by simple clicking into the websites.        








2. Hardware Design
         The hardware design includes the selection of electronics equipment and the integration of all components. Figure below shows the circuit diagram for our project. The specification of every component in showing in figure below is defined in below table. For processing module, we use ESP32. This board is equipped with AWS for communication. ESP32 is compiled using the Arduino programming language. Two LED are used in the project to control their status through AWS.

Table: Hardware Module
Serial number.
Name of equipment
Description
1.
ESP32
Low-power system on a chip micro-controller with integrated Wi-Fi and dual-mode Bluetooth, used to controlled the other hardware equipment and communicate with AWS.
2.
LED
LED’s are used to control their status using ESP32 and AWS
3.
Resistance
Resistances are used to protect the LEDS and as well as ESP32 for any damage due to any inconvenience situation.
4
Breadboard
The whole circuit diagram is made up on this platform


Circuit diagram

Hardware Description
    • ESP32
    The ESP32 development board. If you’re familiar with the ESP8266, the ESP32 is its successor. The ESP32 is loaded with lots of new features.The most relevant, it combines Wi-Fi and Bluetooth wireless capabilities and it is dual core.                   
ESP32 is a low-cost System on Chip (SoC) Micro controller from Espressif Systems, the developers of the famous ESP8266 SoC. It is a successor to ESP8266 SoC and comes in both single-core and dual-core variations of the Tensilica’s 32-bit Xtensa LX6 Microprocessor with integrated Wi-Fi and Bluetooth.

Specifications
   When it comes to the ESP32 chip specifications, you’ll find that:
    • The ESP32 is dual core, this means it has 2 processors.
    • It has Wi-Fi and blue-tooth built-in.
    • It runs 32 bit programs.
    • The clock frequency can go up to 240MHz and it has a 512 kB RAM.
    • This particular board has 30 or 36 pins, 15 in each row.
    • It also has wide variety of peripherals available, like: capacitive touch, ADCs, DACs, UART, SPI, I2C and much more.
    • It comes with built-in hall effect sensor and built-in temperature sensor.

ESP32 pin-out diagram
3.Software Design
 The whole software design divided into two parts,  In this section we discuss them below in brief;
3.1 Software descriptions:
The Arduino IDE: Used for the controlling of the micro-controller ESP32, the IDE has to install some pre-source library from internet, The ESPRESSIF library, ArduinoJson, MQTT library etc. The IDE also used for the integration between the controller and the website via a web-server. The code sketches we used consisted of HTML,CSS and Java-scripts. Some AWS requests also fetched into the sketch. 
The visual studio code: where we built the website framework separately at first using HTML5, CSS3, Java-script and some Bootstrap 5.0 features.
The AWS: Amazon web service is a platform that offers flexible, reliable, scalable, easy-to-use and cost-effective cloud computing solutions.
AWS is a comprehensive, easy to use computing platform offered Amazon. The platform is developed with a combination of infrastructure as a service (IaaS), platform as a service (PaaS) and packaged software as a service (SaaS) offering.
Important AWS Services
Amazon Web Services offers a wide range of different business purpose global cloud-based products. The products include storage, databases, analytics, networking, mobile, development tools, enterprise applications.
AWS Compute Services
Here, are Cloud Compute Services offered by Amazon:
    1. EC2(Elastic Compute Cloud) - EC2 is a virtual machine in the cloud on which you have OS level control. You can run this cloud server whenever you want.
    2. LightSail- This cloud computing tool automatically deploys and manages the computer, storage, and networking capabilities required to run your applications.
    3. Elastic Beanstalk— The tool offers automated deployment and provisioning of resources like a highly scalable production website.
Internet of Things
    1. IoT Core— It is a managed cloud AWS service. The service allows connected devices like cars, light bulbs, sensor grids, to securely interact with cloud applications and other devices.
    2. IoT Device Management—It allows you to manage your IoT devices at any scale.
    3. IoT Analytics—This AWS IOT service is helpful to perform analysis on data collected by your IoT devices.
Migration services used to transfer data physically between your data center and AWS.
    1. DMS (Database Migration Service)-DMS service can be used to migrate on-site databases to AWS. It helps you to migrate from one type of database to another — for example, Oracle to MySQL.
    2. SMS (Server Migration Service)-SMS migration services allows you to migrate on-site servers to AWS easily and quickly.
    3. Snowball—Snowball is a small application which allows you to transfer terabytes of data inside and outside of AWS environment.
Storage
    1. Amazon Glacier- It is an extremely low-cost storage service. It offers secure and fast storage for data archiving and backup.
    2. Amazon Elastic Block Store (EBS)- It provides block-level storage to use with Amazon EC2 instances. Amazon Elastic Block Store volumes are network-attached and remain independent from the life of an instance.
    3. AWS Storage Gateway- This AWS service is connecting on-premises software applications with cloud-based storage. It offers secure integration between the company's on-premises and AWS's storage infrastructure.
Security Services
    1. IAM (Identity and Access Management)— IAM is a secure cloud security service which helps you to manage users, assign policies, form groups to manage multiple users.
    2. Inspector—It is an agent that you can install on your virtual machines, which reports any security vulnerabilities.
    3. Certificate Manager—The service offers free SSL certificates for your domains that are managed by Route53.
Database Services
    1. Amazon RDS- This Database AWS service is easy to set up, operate, and scale a relational database in the cloud.
    2. Amazon DynamoDB- It is a fast, fully managed NoSQL database service. It is a simple service which allow cost-effective storage and retrieval of data. It also allows you to serve any level of request traffic.
    3. Neptune- It is a fast, reliable and scalable graph database service.
Analytics
    1. Athena—This analytics service allows perm SQL queries on your S3 bucket to find files.
    2. Cloud Search—You should use this AWS service to create a fully managed search engine for your website.
    3. Elastic Search—It is similar to Cloud Search. However, it offers more features like application monitoring.
    4. EMR (Elastic Map Reduce)—This AWS analytics service mainly used for big data processing like Spark, Splunk, Hadoop, etc.
Management Services
    1. CloudWatch—Cloud watch helps you to monitor AWS environments like EC2, RDS instances, and CPU utilization. It also triggers alarms depends on various metrics.
    2. CloudFormation—It is a way of turning infrastructure into the cloud. You can use templates for providing a whole production environment in minutes.
Application Services
    1. Step Functions—It is a way of visualizing what's going inside your application and what different microservices it is using.
    2. SWF (Simple Workflow Service)—The service helps you to coordinate both automated tasks and human-led tasks.
    3. SNS (Simple Notification Service)—You can use this service to send you notifications in the form of email and SMS based on given AWS services.
Deployment and Management
    1. AWS CloudTrail: The services records AWS API calls and send backlog files to you.
    2. Amazon CloudWatch: The tools monitor AWS resources like Amazon EC2 and Amazon RDS DB Instances. It also allows you to monitor custom metrics created by user's applications and services.
Developer Tools
    1. Code Star—Code star is a cloud-based service for creating, managing, and working with various software development projects on AWS.
    2. Code Build—This Amazon developer service help you to automates the process of building and compiling your code.
    3. Code Pipeline—It helps you create a deployment pipeline like testing, building, testing, authentication, deployment on development and production environments.
Mobile Services
    1. Mobile Hub—Allows you to add, configure and design features for mobile apps.
    2. Cognito—Allows users to sign up using his or her social identity.
    3. Device Farm—Device farm helps you to improve the quality of apps by quickly testing hundreds of mobile devices.
Business Productivity
    1. Alexa for Business—It empowers your organization with voice, using Alexa. It will help you to Allows you to build custom voice skills for your organization.
The Website: From AWS IoT core registration to attach the certificates, policies into the EC2 and Amazon CA1 root file to the code we build and compile a global website named as “www.arduino.ragadox.com” for client usage purpose. By simply access from the hyperlink anyone can access the whole circuit or system by simple button clicking in the UI.
3.2 The software architecture: 
The following flowchart is shown below that is the major logic of our whole software system or architecture;

Figure 2: The Flow Chart Of the system

The flowchart is divided into two main logic’s that at first the starting of the software work messages have to fetched from the cloud or AWS cloud system then, the messages if existed the micro-controller will be operated by the commands of the sketches and gives the output on the serial monitor which has a baud rate of 115200. The user or occupants can access the whole system if the required commands provided successfully.
Otherwise, on the other hand if the messages will interrupted by technical difficulties then the second condition will fetch and shows the above mentioned errors on the UI of the website like, ERROR 404 etc. And the interaction with the system will be disrupted.

4.Internal System Evaluation results and discussion
    • Making AWS registration with IOT core:
What is AWS IOT core:
AWS IOT core helps us to connect IOT devices to the AWS cloud without the need to provision or manage servers. AWS IOT core can support billions of devices and trillions of messages, and can process and route those messages to AWS endpoints and to other devices reliably and with security. With this facility one can keep track of their applications and communicate with all their devices, all the time, even when they aren’t connected. 
This IOT core supports MQTT(message Queuing and Telemetry Transport), HTTPS(Hypertext Transfer Protocol), LorAwan Network server(LNS) etc.
Creating IOT device in a THING:
To communicate with the ESP32 device, it must connect to AWS IOT core with device credentials. We must also specify the topics it has permission to publish and subscribe on.
    1. In the AWS IOT console, we chose Register a new THING and create a single thing.
    2. Name the new thing as whatever USER want(MyNewESP32 etc.) Leave the remaining fields set to their defaults.
    3. We chose create certificate. Only the thing cart, private key and Amazon root CA 1 downloads are necessary here for the esp32 to connect. Download and save them somewhere secure, as they are used when programming the esp32 device.
    4. Activate and Attached a Policy. Create Register Thing.
    5. In the AWS IOT console side menu, choose secure, policies, we created a policy.
    6. Name the policy as ESP32policy. Chose the advanced tab.
    7. Now we pasted the following code for creating a policy template;
                            
    8. Now replace the REGION with matching AWS region where the user currently operating in.
    9. Replace Account_ID with the owner ID, which can be found in Account Settings, Choose create then, 
    10. In the AWS IOT console, choose secure, Certification. Select the one created for the device and choose actions, attach policy.
    11. At the very end we Chose ESP32policy, and Attached it.
At the end of those processes Our device connected with AWS IOT core by permission. 
Making of the website:
We used the most popular front end languages like HTML5, CSS3, Bootstrap framework and Java script for build a responsive client side website.
At first we build the skeleton of the website by using HTML5 and build some buttons for connecting the LED’s by clicking on it. LED1, LED2 have the ON & OFF features on those buttons made with bootstrap and HTML. In further we integrate those buttons with led and ESP32 via GPIO pins(15, 22 as mentioned before).
We add some CSS to the buttons and give them responsive design and commands by which a user can interact with the website with any mobile and desktop.
Using Java Script we added some script which will help to give a dynamic values to the website and the AWS also can process the request.
The Java-script Comes to handy:
The Java-script helped our project to give some dynamic environment to the website being used by the clients. The JS sketches we made and attached with the previous HTML sketch and then fetch all the logics, requests from the server to the device.
The following sketch is the raw code figure will show a glimpse of our sketch;



Output tested for the first time:
As, we run and upload the codes into the micro-controller the AWS will comes in working condition we can observe some back-end data on the serial monitor of Arduino IDE. The following image shows how the final output comes when we interacted with the ESP32 via website,

Figure shows the serial monitor output when led is being controlled









Keywords: Thing, IOT core, AWS services, Private Key, Certificates.



Running the website for the first time:
After a successful and mentor verified uploading and processing all of the information from AWS to devices we finally saw the first look of our website or better to say client-side;

The final output after applied new designs:
Before getting the final output we evaluated the whole system with new design by means we did some changes into the website coding and we add some status bar by which an user can find and monitor the current status of the LED’s when they are going to interact with them. We add some style to background of the website by CSS and changes the interface by adding some Bootstrap prototype nav-bar which will be fixed in further for better and complete interaction with a established website.
The following website interface will show us the new and modified client-side;
  
CONCLUSION
The proposed system, presents the advancement of Internet technology in day to day life. Our proposed system consists of ESP32, Breadboard, Green LED’s, Jumper wires, 100ohm resistors. The system is suitable for real time small scale industrial process controlling applications. Proposed module implemented on ESP32, one of the best solutions to implement IoT applications. The module outline was tried, actualized and the accuracy and working of the system was verified. The simulation result shows as the LED’s can be accessed from remotely so many other component in further future will be easily controlled by this module. The result is much accurate that it can provide safety from any harm happened than before in any fields. It’s also helps to draw the benefits of use IoT in industry: Elimination of long wiring Web based remote monitoring Immediate action on failures and ease of maintenance.

Recommendation of improvement:
For future purpose, we plan to explore: 1) The usage of camera, so the occupant can find out the current incidents and helps for monitoring the situation; 2) New emergency features will also be provided in further by which one can directly call fire, police, ambulance according to the importance of the situation; 3) New advanced status report will be assembled by which user can find more efficient and accurate data of the current instances; 4)With using relay modules we can create a whole lightning control system. 








References
    1. 4th International Conference on Computer Science and Computational Intelligence 2019 (ICCSCI), 12–13 September 2019 Door Security System for Home Monitoring Based on ESP32 Andreasa, Cornelio Revelivan Aldawiraa , Handhika Wiratama Putraa , Novita Hanafiaha, Surya Surjarwoa , Aswin Wibisuryab. (andreas2019.pdf (sci-hub.se))
    2. Wukkadada B, Wankhede K, Nambiar R, Nair A. Comparison with HTTP and MQTT In Internet of Things (IoT). In Proceedings of the International Conference on Inventive Research in Computing Applications (ICIRCA 2018); 2018; Coimbatore. p. 249-253
    3. Prabaharan J, Swamy A, Sharma A, Bharath KN, Mundra PR, Mohammed KJ. Wireless Home Automation and Security System using MQTT Protocol. In 2017 2nd IEEE International Conference On Recent Trends In Electronics Information & Communication Technology; 2017; Bangalore. p. 2043-2045.
    4. Su, J. (2019). Amazon Owns Nearly Half Of The Public-Cloud Infrastructure Market Worth Over $32 Billion. Forbes. Available online: “https://www.forbes.com/sites/jeanbaptiste/2019/08/02/amazon-owns-nearly-half-of-the-public-cloud-infrastructure-market-worth-over-32-billion-report/?sh=4e369bf929e0 “(accessed on 6 December 2020).
    5. National Institute of Standards and Technology, NIST.2011. The NIST Definition of Cloud Computing.
    6. The AWS documentation page etc.


  
