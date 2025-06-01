# ELDEREASE-health-app
import time
import datetime
from plyer import notification

def remind(title, message):
    notification.notify(
        title=title,
        message=message,
        timeout=10  # shows for 10 seconds
    )

# Reminder intervals in seconds (customize as you want)
WATER_INTERVAL = 60 * 60  # every 1 hour
MEDICINE_INTERVAL = 60 * 180  # every 3 hours
WALK_INTERVAL = 60 * 120  # every 2 hours

# Last alert times
last_water = time.time()
last_medicine = time.time()
last_walk = time.time()

print("ElderEase Health Reminder is running...")

while True:
    current_time = time.time()

    if current_time - last_water >= WATER_INTERVAL:
        remind("💧 Drink Water", "Time to drink some water!")
        last_water = current_time

    if current_time - last_medicine >= MEDICINE_INTERVAL:
        remind("💊 Take Medicine", "Time to take your medicine.")
        last_medicine = current_time

    if current_time - last_walk >= WALK_INTERVAL:
        remind("🚶 Walk Time", "Take a short walk or stretch.")
        last_walk = current_time

    time.sleep(60)  # check every minute

    
  
