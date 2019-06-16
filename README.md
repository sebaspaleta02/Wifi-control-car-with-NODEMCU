# Wifi-control-car-with-NODEMCU/*Created in M�xico:
 * Edited by: Sebastian M. P. 
 * For using this arduino program you will need a NODEMCU8266 
 * This dll will help you to control the car via Wifi 
 *********Read the instructions to know how to use it in Windows Forms 
 */
/*Created in M�xico:
 * Edited by: Sebastian M. P. 
 * For using this arduino program you will need a NODEMCU8266 
 * A small car with two motors 
 * One L298 to control the two motors 
 * Batteries 18650 and a battery holder 
 * Cables (jumpers ) to connect the NODE and the L298
 * This program can be modified to control the speed of the motors 
 * A switch if you want to turn off the car easily 
 * Power bank to give the NODE enough battery and control it remotely via WIFI
 * 
 * ++L298 pin assignment: 
 * ++NODEMCU D0 to IN1 of L298
 * ++NODEMCU D1 to IN2 of L298
 * ++NODEMCU D2 to IN3 of L298
 * ++NODEMCU D3 to IN4 of L298
 * ++NODEMCU G (GND) to GND of L298
 * ---Do not remove the ENB
*/

----------------------------------------------------------Steps to add the dll 

1. Download the dll and save it in the desktop
2. Open a new C# Windows Form 
3. Add this new References to the new program you created copy and paste them at the very top
"using System.Net.Http;"
"using System.Net;"
"using System.Net.Sockets;"
4. Open the dll Example: C:> Users> USER > Desktop > dll car> car wifi > car wifi > bin > Debug
When you have reached the folder Debug Copy the two files called 
*car wifi.dll*
*car wifi.pdb*
5.Open the folder of the new program you created Example C:> Users >USER >Desktop> car >car
There you will see a folder and a file that open the program, open the folder and paste the two files that we copied 
6. Return to the new form were we added the references, go to the right side to "Solution Explorer" 
there you will see just below "Solution "name of the proyect"" right click in the one below of this one the green one it show only the name of your proyect, example: "car"
7. After that a list of properties is going appear click the one that says "Add>" followed by "Existing item"(the green one) a folder will open, go to the Drop down list and select the one that says
"All the files(*.*)" select both of the files that we copied earlier and click in "add |v" 
8.Below "Solution "name of the proyect"" there is one called "References" right click and a small window will apear click at the one that says "Add reference..." a big window is going to appear so we are going to the left side below ">COM" there is one called 
">Examine" we click that one, inside of that one we are going to give click on "Examine..." a folder is going to open right there we are going to search our dll folder we open it and go to 
Example: C:>User>USER>Desktop>dll car>car wifi>car wifi>bin>Debug when we reach the folder Debug we are going to see our dll example: car wifi.dll we click and then we click "Add |v"
9.When completed all the above steps we have to add a new reference "using car_wifi;" just below the other ones we already added copy this and paste just below "using System.Net.Sockets;" 
10. At the new Windows Forms add two textBox and a timer1 
11.Double click to the form and put copy this  "timer1.Enabled = true;"
12.Double click to the timer1 and add the "async" metod "private async void timer1_Tick"
13.Add this lines of code inside of the timer:

 try
 {
 obj.all(textBox1.Text.ToString(), Convert.ToChar(textBox2.Text));
 textBox2.Clear ();
 }
 catch
 {}

14. The first textBox1 is going to be your ip that we added in arduino example of what are you going to writte when you start the program [192.165.345] only the numbers and the dots no spaces
15. The second text box is for the directions of the car 
the following keys are the directions that you are going to writte while the program is running same with the ip :

w=Foward
a=left
s=Backwards
d=Right
c=Stop

----------------------------------------Steps to add the... wifiIp,wifiNet,wifiGW to arduino 
Example IPAddress wifiIp(192,128,1,200);
Example IPAddress wifiNet(225,225,225,1);
Example IPAddress wifiGW(192,128,1,1); 

1. WIN+R it will open a command window 
2. Writte "cmd"
3. It will open a black window 
4. Writte "ipconfig"
5. Then a list of directions will show
STEP 6 IS FOR wifiIp 
STEP 7 IS FOR wifiNet 
STEP 8 IS FOR wifiGW 
6. Search the one that says "Address IPv4" or "Address IPv6" that line is going to give you the IP of your computer copy that numbers and paste them in IPAddress wifiIp(#numbers); located in the arduino program IMPORTANT THE NUMBERS YOU COPIED ARE THE IP OF YOUR COMPUTER SO YOU HAVE TO CHANGE THE LAST NUMBER EXAMPLE WE COPY
192,128,1,200 CHANGE THE LAST NUMBER 200 FOR A 201 OR 202 YOU CAN DECIDE THE NUMBER 1-9 
7.  this one is located just below of step 6  ("Address IPv4") and it shows four big numbers Example 225,225,225,1 copy them and paste them in arduino in the line IPAddress wifiNet(#Numbers);
8. it is located just below step 7 the first line are some strange numbers then below those numbers is a line with similar numbers to your ip copy them and paste them in arduino in the line wifiGW(#numbers); 
9. upload the program to the NODEMCU and it is ready to use 

___________________Example of the final result 

-first text box you writte your ip that was assinged *remember to use dots and do not use spaces while writting the ip   :[192.200.134.340] 
-second text box is for directions [w],[s],[d],[a],[c]


Thanks boys! good luck hope i explained well to you and you can use this proyect :)
