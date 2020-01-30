# project-1
Introduction:
	The purpose of this project is to understand what is CTD, how they take data and how they convert data.
  CTD stands for Conductivity, Temperature, and Density. It’s a package of electronic instruments that
  dive deep or shallow into the ocean and It directly measures conductivity, temperature, and pressure.
  Based off that data it can calculate salinity, density, depth, and speed of sound.
	Using an online website that has multiple measuring devices in the ocean, data can be grabbed from those 
  different measuring devices. The devices include the Oregon Shelf Surface Piercing Profiler Mooring, the
  Oregon Offshore Cabled Shallow Profiler Mooring, the Oregon Offshore Cabled Deep Profiler Mooring, the
  Oregon Slope Base Shallow Profiler, the Oregon Slope Base Deep Profiler, the Axial Base Shallow Profiler,
  and The Axial Base Deep Profiler.
	For each of these devices, 24 hours of data was downloaded and then analyzed using Python. From the data,
  speed of sound is graphed against the depth of the water for each dive in the 24-hour span. The average
  speed of sound is also calculated for each depth point for all the dives, and lastly the maximum speed 
  of sound value was found for each dive of all the devices. 
	For the winter, data was taken during anytime between December 20th through the 26th. Due to limited data 
  this also spans from 2015 to 2019 for different devices. The same is true for the summer but it ranged anywhere
  from August 20th through the 31st.
  
  Explaination of Code:
•	Cell 1 grabs the raw data of the downloaded 24-hours of data from the device that will be in the same github file as the code.
•	Cell 2 converts the data file, which is CSV, and converts it to a dataframe
•	Cell 3 then takes certain parameters from the dataframe and puts them into arrays
•	Cell 4 then takes the pressure and density and calculates depth of the water for every point and then
  calculates speed of sound in the water using temperature, salinity, and the depth of water
•	Cell 5 converts the depth (x) and speed of sound (y) arrays to actual integer values in an array
•	Cell 6 goes through the entire depth array to find when the device starts a new dive, at that point, 
  the corresponding index is recorded in a new array called ‘v’ and the number of dives goes up 1 to determine how many dives there are
•	Cell 7 splits the depth and speed of sound array into multiple arrays that correspond to each dive
•	Cell 8 goes through each split array in the speed of sound to determine the max value for each dive
•	Cell 9 incorporates a nested loop, the for loop in the while loop averages the same index for each dive 
  and the while loop moves onto the next index. The average speed of sound value is stored in ‘y2’ and the average 
  depth at each index is stored in ‘x2’.
•	Cell 10 plots the graph of all the dives where depth is on the x axis and speed of sound is on the y axis
•	Cell 11 plots the average speed of sound of all the dives against depth.
•	Cell 12 prints out the max value of each dive.
![alt text](https://github.com/stokljos/project-1/blob/master/Peircing%20Mooring%20Graphs.JPG)
Analysis:
1.	Compare the number of dives per day of the shallow profiler vs deep profiler

For the offshore Cable profiler, the Deep profiler has 13 dives in the winter and 7 dives in the summer 
compared to the shallow profiler which has 5 dives in the winter and 6 dives in the summer. For the Oregon 
Slope Base Profiler, the shallow profiler for winter and summer have 6 and 7 dives compared to the deep profiler 
that has 2 dives. Lastly for the Axial Base Profiler, the shallow profiler has 7 dives in both the summer and winter, 
and for the deep profiler, there are 3 dives for the winter and summer.
It makes sense that the shallow dives are more frequent than the deep dives because the deep dives take longer as 
they cover more depth. It is interesting that for the offshore cable profiler that the deep dive has almost twice as
many dives as the shallow one. The shallow profiler could have been having problems that day possibly or other difficulties.

2.	Where is the maximum value of ssp in each season? Explain why the max ssp should be there?

For all the profilers, the maximum speed of sound is higher in the summer than in the winter. This is because when it’s 
cold out the molecules are closer together, making it difficult for the sound to travel, but when it is warmer, the 
molecules are farther apart making it easier to travel between them.

3.	Compare the ssp profile in day and night of all profilers, explain what you find (effect of day vs night).

All the data starts at 19:00 which would be 6 pm, initially in the graphs, it shows that the first couple dives slope 
lower which means the speed of sound decreases more rapidly than the last half of the dives which decreases slower. This 
is because at night, it become colder causing the speed of sound to decrease. But as it warms up during the day causing 
the temperature to rise, the speed of sound doesn’t decrease as much as depth inceases.

4.	Compare the ssp profile in summer and winter of all profilers, explain what you find (effect of season)

The speed of sound is slower in the winter, this is because of the same reason as the answer to question 2. Colder the temperature, 
the harder it is for the speed of sound to travel.

5.	Compare the average ssp profiles of all profilers recorded at the same day in winter and summer (effect of location).

Unfortunately, due to limited data, it was impossible to get data for all the profilers on the same day, some are from 
different years than others but they are all around the days in the same months so they can still be compared.
	It’s interesting that the Oregon slope base deep profiler in the winter and summer, and the axial base deep profiler 
  in the summer and winter have their averages of ssp increase as depth is increased. Looking into the data, it shows 
  that the temperature is stays consistent through the data without much change, and the density is very high compared
  to the other data sets. Because of this, it causes an increase in ssp as depth increases so the averages increase. 
	As for the other graphs, they all decrease in speed of sound as depth increases, and when it hits a certain depth, 
  the slope levels out at a speed of sound value, for shallow profilers it’s around 100 to 150 meters and for the deep 
  profilers, it’s more around 400 to 500 meters.

