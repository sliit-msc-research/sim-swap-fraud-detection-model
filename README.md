# sim-swap-fraud-detection-model
Data Set Definition 


sim_swap_time_gap_minutes	The time difference in minutes between the last SIM change and the current OTP request.
💡 A low value (e.g., 1–2 mins) may indicate a fraud attempt, as fraudsters typically request OTPs shortly after swapping the SIM.
sim_swap_flag	A boolean label indicating whether the record is a confirmed SIM swap fraud case (true) or not (false). Used as the ground truth for training/evaluation.
device_change_flag	Indicates whether the device (e.g., IMEI) has changed compared to historical records.
💡 True = suspicious if changed with SIM.
sim_type_change_flag	Indicates whether the type of SIM (e.g., physical to eSIM) changed.
💡 May signal fraud or device upgrade — needs correlation.
imsi_change_flag	IMSI = International Mobile Subscriber Identity. A change indicates the user swapped SIMs.
iccid_change_flag	ICCID = SIM card identifier. Change means SIM card was physically replaced.
otp_and_sim_change_geo_hash_length	This reflects the geohash prefix length shared between the location of the SIM change and the location of the OTP request.
💡 A shorter shared prefix (e.g., 2–4) means locations are far apart, suggesting suspicious behavior. A longer match (e.g., 9–10) means the OTP was requested from the same/nearby location
