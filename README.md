# overkill-alarm-clock
Time driven LEDs for wake up and bedtime reminders

# Goal:
Leds will turn on based on day of week, time of day, and current state. *see states below*

# Hardware:
- [3 SUPERNIGHT 16.4FT 5M SMD 5050 Waterproof 300LEDs RGB Color Changing Flexible LED Strip Light](https://www.amazon.com/gp/product/B00DTOAWZ2/ref=oh_aui_search_detailpage?ie=UTF8&psc=1)
- 1 Raspberry pi
- some transistors to control leds

# Software
Will be using Node.js unless convinced otherwise.

# States:
1. Inactive
  - used at night 
  - leds off
2. Wake
  - switch from Inactive to Wake if day != weekend and time == wake alarm time
  - leds come on white
3. Bedtime
  - switch from Manual to BedTime if time == bed alarm time
  - leds pulse brightness (maybe someday pulse every 5 minutes)
4. Manual
  - used durring day
  - leds follow remote (maybe someday)
  
```
[-----------]
[           ]
[   Wake    ]
[           ]
[-----------]
      |  ^
button|  |time
 press|  |check
      |  |
      v  |
[-----------]   button  [-----------]
[           ]<----------[           ]
[ Inactive  ]           [  Manual   ]
[           ]---------->[           ]
[-----------]   button  [-----------]
      ^                       |     
      |                       |     
      |button                 |time
      |     [-----------]     |check 
      |     [           ]     |     
      |-----[  Bedtime  ]<----|   
            [           ]
            [-----------]
```
