# COMport
The two programs are a result of fiddling with IOT-stuff (Arduino, ESPxxxx etc) where I needed to know the name of COM-ports either new or gone.
<br>You may of cause use the Management Console, but I would like to have something running that would tell me of changes on the COM-port(s) without having to do any program start.
<br>Hence came the idea of a Service and a Desktop application that would run each time the computer is started without any further due.
## COMportService
This is a service program being started by a timer every 10 second<br>
It will check for any change in COM-ports on the machine.<br>
In case of changes they will be written to a status-file and a Desktop application will be started
## COMportDesktop
This is the desktop program being started by the service when a change in COM-port is detected (removed or added).
<br>It is a small and very simple program that have three lists: New, Gone and Existing.
<br>The program is a pure "display info" type of program, the only user interaction is the Exit-button.
## Configuration
The configuration required is added to the programs at initial startup of the Service. 
<br>Use the "Start parameters:" field to add the two required parametes:
<ul>
<li>Full path to COMportDesktop.exe
<li>Full path to the status-file. This is the file used to write detected changes by the service in order to be read and displayed by the Desktop application
</ul>
Example of an entry:<br>
C:\Users\roara\source\repos\COMportDesktop\COMportDesktop\bin\Release\COMportDesktop.exe C:\Temp\COMportStatus.txt
<br>The Service will also write information to a log-file (COMportService.log). This file is located in the bin-folder of the Service
(for instance: C:\Users\roara\source\repos\COMportService\COMportService\bin\Release\COMportService.log)

