# Operational Notes

The following recommendations will help ensure reliable operation of the MicroRider-1000 throughout the survey.

---

## Battery Charging

- Charge the external battery every **2–3 days**, or sooner if required.
- A fully charged battery will typically power the MicroRider for multiple profiles (approximately 10 profiles under normal operation).
- Recharge the battery before it becomes fully discharged.

---

## Daily Communication Check

At least once per day:

1. Connect to the MicroRider using the communications procedure.
2. List the contents of the **data** directory.

```text
dir data
```

3. Verify that one new data file has been created for each completed profile.

!!! note

    The number of data files should increase by one after each successful deployment. This provides a simple confirmation that the instrument is recording data correctly.

---

## Unable to Communicate with the Instrument

If communication cannot be established:

- Verify the external battery is charged.
- Confirm the deck unit is switched on.
- Confirm the USB cable is connected.
- Check **Device Manager** and confirm the correct COM port is being used.
- Verify that Tera Term is connected to the correct serial port.
- Refer to the **Communications & Download Data** procedure if necessary.
- Disconnect and reconnect the deck cable.
- Restart the deck unit and try again.

---

## Suspected Probe Damage

If the frame contacts the seabed or the probes are suspected to have been damaged:

- Inspect all probe tips carefully.
- Do not continue using visibly damaged probes.
- Download the recorded data before removing the probes.
- Contact the NorGliders team if you are unsure whether the probes remain suitable for deployment.

---

## Data Quality

It would be greatly appreciated if one or two representative data files could be sent to the NorGliders team during the survey.

This allows us to:

- verify the instrument configuration,
- assess the quality of the turbulence measurements,
- identify potential problems early,
- provide recommendations before additional profiles are collected.

Early review of the data can often prevent the loss of valuable measurements.

---

## Further Assistance

If you encounter a problem that cannot be resolved using this guide, please contact the NorGliders team and provide:

- a description of the problem,
- the most recent data file,
- any relevant terminal output or error messages,
- photographs of the instrument or probes if damage is suspected.