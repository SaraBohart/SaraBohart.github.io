---
title: Power Budget
tags:
- tag1
- tag2
---
![Power Budget image](https://github.com/user-attachments/assets/2544c893-83b7-4d2f-ac78-ac545136ba45) <br>
By making this power budget, I was able to gage what power source I would need. It allowed me to estimate the necissary voltage and current to supply to my system. <br>
This power budget assumes that the system will be powered using an outlet via an adapter such as [this](https://www.amazon.com/Adapter-Signcomplex-100-240V-Transformers-Switching/dp/B074HRM5D4?source=ps-sl-shoppingads-lpcontext&ref_=fplfs&smid=A3AI1Y9BXQD9K&th=1). Since the power source is an outlet and not a battery, the battery life is inefinite. It makes more sense for this project to be powered through a stationary wall outlet because it would be used in an enviornment like a museum, where the motor will not need to be transported often.<br>
This is a [PDF of the Power Budget](https://github.com/user-attachments/files/20047875/UpdatedPowerBudget.pdf), which can be downloaded for easier viewing.
Durring testing, the original H-Bridge caught on fire. It was though that this issue was caused by the 4 amp power supply, so the amprage was brought down to 2. [This](https://www.amazon.com/dp/B086T1N5R4?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1) is the powersource that was used at the innovation showcase. It had enough power to power the whole team and the motor.
## Conclusion
Even though I calculated that I needed a 4 amp power supply, I used a 2 amp power supply. This was because when I plugged one of my original motor drivers into the full 12V 4A power, it burnt. The power budget is based on the absolute maximum current needed for the system. My system does not constantly run at the maximum current, theirfore it worked just fine with half of the maximum needed ampherage. A power budget is great for estimating the maximum current needed, but the data sheets must be consulted to ensure that the components can all run with that maximum current.
