## 1.1 Lesson Plan: Getting Started with Wireshark

### Overview

In today's class, students will start using wireshark. They will gain an understanding of how packets flow in and out of a network interface, what capture and display filters are, and how to use them to narrow the scope of packet analysis.

### Objectives

By the end of class, students will be able to:

* Understand how packets flow into and out of an interface.
* Explain the difference between a capture filter and a display filter.
* Demonstrate how to select the proper interface for a packet capture.
* Demonstrate how to set a capture filter.
* Demonstrate how to set a display filter.

### Instructor Notes

* In today's class there will be moments where students will get lost in the overwhelming number of packets they will be sorting through with WireShark.  Encourage them by telling them that it's all about finding the right filter to drill down into the data they are looking for.  If the material seems to easy for some students, remind them that they are only getting started with WireShark and there are many more advanced features. The skills learned today are foundational to success in packet analysis.

----

### 1. Direct Instruction: Understanding Interfaces and Filters. (0:15)

* Welcome the students to their first real dive into network packet analysis and explain that packet analysis is key to many cybersecurity functions to include malware analysis, threat hunting, and network defense. 

* Use the slides to guide your discussion.

* Explain why packet analysis is important. Explain that a packet capture is an exact replica of network traffic just as it traveled across the wire and into the device's interface. This is key for things like troubleshooting a connection problem, discovering the source of an attack, recovering passwords or other sensitive data that is not properly protected, and forensic analysis in some computer crimes.

* Explain what WireShark is. Be sure to emphasize that it is NOT just a packet capture tool. It is a complete packet analysis package. Take a moment to describe each of the features listed on the slide. Highlight how well WireShark is with displaying detailed protocol information.

* Describe the process by which a network packet arrives at a computer. Be sure to explain that a network interface is a point of connection to the network. If the network trusts the system (e.g. it isn't blocked by a firewall), it will communicate with it using the protocols that govern computer communication (Ethernet,TCP,UDP,DNS,etc.).

* Take a moment to describe how to select one or more interfaces to capture on in WireShark. Describe how some systems will have many interfaces, but with a little thought it's easy to determine which to select.

* One of WireShark's most powerful and useful features is filtering. Ensure you explain this to students and reiterate that it is key to successful packet analysis with WireShark. Detail how capture filters work to only capture desired packets and display filters are used to "hide" collected packets once they have already been captured. If you have some powerful filters that have served you well, now is the time to share them. If you have students in the classroom that have used Wireshark extensively, ask them to share their favorite filters.

* Take a moment to walk students through the main WireShark window. Briefly explain each section. There's no need to go into great detail at this time, but for the guided practice students need to know the names of the areas in the main window.

* Ask the students if they have any questions about interfaces or filters before moving on to the guided practice.

### 2. Guided Practice: Select an Interface and Filters to Capture and Display Traffic (0:15)

* Have students open Wireshark.

* Tell the students that the point of this guided practice is to learn how to capture traffic and understand the power of filters. If they do not fully understand what the filter is doing, it's okay. Wielding WireShark filters effectively takes time and research to find the filter that they'll need for a given circumstance.

* Send students the following instructions.

* **Instructions:**

  #### Select an Interface and Start Capturing (0:05)

  * Take a look at your list of interfaces. You'll want to determine the interface that you are using to surf the web. If you already know, great!  If you don't, just follow the quick test listed below to figure it out. This method will work no matter which operating system you are using.
  
    * Take a look at the list of interfaces in Wireshark. To the right of each listed interface there is a graph that represents the flow of packets. You are going to cause some traffic to flow and observe it here.
    * Navigate to https://www.google.com/search?q=speed+test 
    * Click the blue "RUN SPEED TEST" button
    * Watch the graphs in Wireshark. You will see a spike in traffic on the interface on which the speed test is being performed. This is the interface you will select.

  * Click the appropriate interface to highlight it in blue.
  * In the WireShark main toolbar, click the blue shark fin to start capturing traffic.
  * Next, navigate to https://www.wireshark.org/ and click a few links to generate some additional traffic on your interface.
  * After WireShark has been capturing packets for at least 60 seconds click the red square in WireShark's main toolbar to stop capturing packets.
  
  #### Use a Display Filter (0:07)
  So far in this guided practice session, you have captured every packet that has passed through your interface. To make sense of it, you'll want to use a few display filters. We are going to take a look at the traffic we generated while navigating to wireshark.org. However, this is a bit tricky because, if you remember, https requests encrypt the host name and only the ip address is in clear text. No worries, let's use a display filter for the DNS protocol to find the ip address for wireshark.org.
  
  * In the display filter input box enter `dns.qry.name == "wireshark.org" && dns.flags.response==1`. This filter looks a bit complex so let's break it down.
    * The filter to the left of the logical AND (&&) is telling WireShark to find DNS queries for wireshark.org
    * The filter to the right of the logical AND is telling WireShark to only display DNS responses.
    * The end result is DNS responses for wireshark.org
  * WireShark places DNS responses in the Info field of the packet list pane for convenience. We can see the ip address for wireshark.org is 104.25.219.21
  * Click the X on the right side of the display filter box to clear the current filter.
  * Enter the following filter and press enter. `ip.addr == 104.25.219.21`
  * You should now see only the communication between your computer and wireshark.org (104.25.219.21). Right-click on the first frame and select `Follow > TCP Stream`
  * Note that everything is encrypted. You can't determine anything except the host and amount of traffic. This shows how important https is when using web applications.
  
  Congrats! You just performed a bit of packet analysis. Next, let's use a capture filter.
  
  #### Use a Capture Filter (0:03)
  
  * Select `File > Close` from the menu and select `Continue without saving` to clear the current capture.
  * Ensure the appropriate interface is still selected.
  * In the capture filter input box enter `port 53` (DNS traffic travels over port 53 by default)
  * Click the blue shark fin to start the capture.
  * Navigate to http://www.nmap.org/
  * As soon as the site loads, stop the capture by clicking the red square in the main toolbar.
  * You should now only see DNS packets. Can you filter out the response packets for nmap.org?
  
* **BONUS:** Did you finish early? Navigate to https://wiki.wireshark.org/CaptureFilters or https://wiki.wireshark.org/DisplayFilters and try some other interesting filters.
