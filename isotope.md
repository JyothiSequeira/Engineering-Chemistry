import math 

import matplotlib.pyplot as plt





# input for isotope 1

initial_mass_1 = float(input("Enter initial mass of isotope 1 (grams): ")) 

half_life_1 = float(input("Enter half-life of isotope 1 (in years): "))





# input for isotope 2

initial_mass_2 = float(input("Enter initial mass of isotope 2 (grams): ")) 

half_life_2 = float(input("Enter half-life of isotope 2 (in years): "))



# Total observation time 

total_time = int(input("Enter total time for observation (in years): "))



#list for all value

time_intervals = [] 

remaining_mass_1 = [] 

remaining_mass_2 = []



# calculation

for t in range(0, total_time + 1, total_time // 10 or 1):  #(10 intervals)

    mass_1 = initial_mass_1 * (0.5 ** (t / half_life_1))

    mass_2 = initial_mass_2 * (0.5 ** (t / half_life_2))

    time_intervals.append(t)

    remaining_mass_1.append(mass_1)

    remaining_mass_2.append(mass_2)

    

# Plotting

plt.plot(time_intervals, remaining_mass_1, marker='o', linestyle='-', color='r', label="Isotope 1") 

plt.plot(time_intervals, remaining_mass_2, marker='x', linestyle='-', color='b', label="Isotope 2") 

plt.xlabel("Time (years)") 

plt.ylabel("Remaining Mass (grams)") 

plt.title("Radioactive Decay of Two Isotopes") 

plt.legend() 

plt.grid(True) 

plt.show()

