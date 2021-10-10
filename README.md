# WinTimeShifer
The script shifts the windows' time step by step to fix the time difference smoothly.

To use it you should at first modify it a bit. There are three variables:
1. Increment in seconds, ususally float because you need in milliseconds to make time shifting smooth. 100 ms is fine. It must be positive if you need to increase the Windows' time. Otherwise, if you need to decrease the time, then use negative value.
incr = 0.1 

2. The time difference in seconds value which has to be fixed.
timeShift = 160

3. Step interal, seconds. It's time between each step.
interval = 20 

If you are gonna use that script on a data server with broken time, you should first try to set incr <= 0.1 and interval >= 20 to prevent corruption of timestamps.
Also there are some delays in Windows' time service and maybe another programs which affect on the Window's time. 
It means that your increment may cause bigger or smaller time shift than you have set. 
That's why you should to test the script first with smaller parameters. Otherwise your time can be changed too fast or too slow. 
For example, in my case incr = 0.1 caused 300 ms shift per step approx and -0.6 caused the same 300 ms shift but for decreasing the time. 
