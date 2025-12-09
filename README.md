from datetime import datetime, timedelta

print("----- DESTINATION PREDICTOR -----")
name = input("Enter your name: ")

# ---- 1. Get the distance (Validated)
while True:
    Distance_input = input("Input Destination's Distance in Km: ")

    try:
        Distance_km = float(Distance_input)
        break   # <-- Add this so the loop stops after correct input

    except ValueError:
        print("Please enter a valid number, try again.\n")
 #---- 2. Get the speed(validated)
while True:
 	speed=(input("Enter Average Speed rate(Km/h)")) 
 	try:
 		speed_input=float(speed)
 		break   # <-- Add this so the loop stops after correct input
 		
 	except ValueError:
 		print("Please enter a valid number, try again.") 
#----- 3. Get the current_time (validated)
while True:
	current_time=input("Enter current time(HH:MM):")
	break   # <-- Add this so the loop stops after correct input
#Convert Input to Actual time 
Actual_time=datetime.strptime(current_time, "%H:%M")
	

#---- 4. Calculate travel time
Time_needed=Distance_km / speed_input
# Covert travel time to delta
travel_delta=timedelta(hours=Time_needed)

#---- 5. Calculate Arrival time
arrival_time = (Actual_time + travel_delta)
# Show result in HH:MM format
print(name, "You will arrive at:", arrival_time.strftime("%H:%M"))  
