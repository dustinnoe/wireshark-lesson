## 1.1 Lesson Plan: Getting Started with Wireshark

### Overview

In today's class, students will start using wireshark. They will gain an understanding of how packets flow in and out of a network interface, what capture and display filters are and how to use them to narrow the scope of packet analysis.

### Objectives

By the end of class, students will be able to:

* Understand how packets flow into and out of an interface.
* Explain the difference between a capture filter and a display filter.
* Demonstrate how to select the proper interface for a packet capture.
* Demonstrate how to set a capture filter for a specific host.
* Demonstrate how to set a display filter for ARP, HTTP(S), DNS, and other protocols.

### Instructor Notes

* In today's class there will be some moment's where student's will get lost in the overwhelming number of packets they will be sorting through with WireShark.  Encourage them by telling them that it's all about finding the right filter to drill down into the data they are looking for.  If the material seems to easy for some students, remind that they are only getting started with WireShark and there are much more advanced features. The skills learned today are foundational to success in packet analysis.

* Review the 

----

### 1. Direct Instruction: Understanding Interfaces and Filters. (0:15)

* Welcome the students to their first real dive into network packet analysis and explain that packet analysis is key to many cybersecurity functions to include malware analysis, threat hunting, and network defense. 

* Use the slides to guide your discusion.

* Explain why packet analysis is important. Explain that a packet capture is an exact replica of network traffic just as it traveled accross the wire and into the device's interface. This is key for things like troubleshooting a connection problem, discovering the source of an attack, recovering passwords or other sensitive data that is not properly protected, and forensic analysis in some computer crimes.

* Explain what WireShark is. Be sure to emphasize that it is NOT just a packet capture tool, it is a complete packet analysis package. Take a moment to describe each of the features listed on the slide. Highlight how well WireShark is with displaying detailed protocol information.

* Describe the process by which a network packet arrives at a computer. Be sure to explain that a network interface is a point of connection to the network. If the network trusts the system (e.g. it isn't blocked by a firewall), it will communicate with it using the protcols that govern computer communication (Ethernet,TCP,UDP,DNS,etc.).

* Take a moment to describe how to select one or more interfaces to capture on in WireShark. Describe how some systems will have many interfaces but with a little though it's easy to determine which to select.

* One of WireShark's most powerful and useful features is filtering. Ensure you explain this to students and reiterate that it is key to successfull packet analysis with WireShark. Detail how capture filters work to only capture desired data and display filters are used to "hide" collected packets once they have already been captured. If you have some powerful filters that have served you well, now is the time to share them. If you have students in the classroom that have used Wireshark extensively, ask them to share their favorite filters.

* Ask the students if they have any questions about interfaces or filters before moving on the to the guided practice.

### 2. Guided Practice: Select an Interface and Filters to Capture and Display Traffic (0:15)

* Have students open Wireshark

* Send students the following instructions.

* **Instructions:**
  #### Select an Interface and Start Capturing
  a) Take a look at your list of interfaces. You'll want to determine the interface that you are using to surf the web. If you already know, great!  If you don't following the test listed below. This method will work no matter which operating system you are using.
     1. Take a look at the list of interfaces in Wireshark. To the right of each listed interface there is a graph that represents the flow of packets. You are going to cause some traffic to follow and observe it here.
     2. Navigate to https://www.google.com/search?q=speed+test 
     3. Click the blue "RUN SPEED TEST" button
     4. Watch the graphs in Wireshark. You will see a spike in traffic on the interface where where the speed test is being performed. This is the interface you will select.
     
  b) Click the appropriate interface to highlight it in blue.
  c) In the main WireShark tookbar click the blue shark fin to start capturing traffic.
  d) Next, navigate to https://www.wireshark.org/ and click a few links to generate some additional traffic on your interface.
  e) After WireShark has been capturing packets for at least 60 seconds click the red square in WireShark's main toolbar to stop capturing packets.
  
  #### Use a Display Filter
  So far in this guide practice session, you have captured every packet that has passed through your interface. To make sense of it, you'll want to use a few display filters. We are going to take a look at the traffic we generated while navigating to wireshark.org
  
  a. In the display filter input box enter `dns.qry.name == "wireshark.org" && dns.flags.response==1`.
  
  
  #### Use a Capture Filter
* Let the class know that, by the end of the week the will be able to confidently capture and analyze traffic on the network they are responisble for.
