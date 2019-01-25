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

* 

* Use the slides to guide your discusion.

* Explain why packet analysis is important. Explain that a packet capture is an exact replica of network traffic just as it traveled accross the wire and into the device's interface. This is key for things like troubleshooting a connection problem, discovering the source of an attack, recovering passwords or other sensitive data that is not properly protected, and forensic analysis in some computer crimes.

* Explain what WireShark is. Be sure to emphasize that it is NOT just a packet capture tool, it is a complete packet analysis package. Take a moment to describe each of the features listed on the slide. Highlight how well WireShark is with displaying detailed protocol information.

* Describe the process by which a network packet arrives at a computer. Be sure to explain that a network interface is a point of connection to the network. If the network trusts the system, it will communicate with it using the protcols that govern computer communication (IP,TCP,UDP,DNS,etc.).

* Take a moment to describe how to select one or more interfaces to capture on in WireShark. Describe how some systems will have many interfaces but with a little though it's easy to determine which to select.

* One of WireShark's most powerful and useful features is filtering. Ensure you explain this to students and reiterate that it is key to successfull packet analysis with WireShark. Detail how capture filters work to only capture desired data and display filters are used to "hide" collected packets once they have already been captured. If you have some powerful filters that have served you well, now is the time to share them. If you have students in the classroom that have used Wireshark extensively, ask them to share their favorite filters.

* Ask the students if they have any questions about interfaces or filters before moving on the to the guided practice.

### 2. Guided Practice: Select an Interface and Filters to Capture and Display Traffic (0:15)

* Let the class know that, by the end of the week the will be able to confidently capture and analyze traffic on the network they are responisble for.
