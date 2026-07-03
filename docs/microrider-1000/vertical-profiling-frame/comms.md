# Program and Bench Test

Configure the MicroRider-1000 and perform a bench test using the factory-installed test probes.

!!! note "Test probes"

    Perform this procedure with the factory-installed test probes fitted. Install the shear and FP07 probes only after the bench test has been completed successfully.

## Procedure

### 1. Connect the Instrument

<photo>

1. Connect the deck cable to the MicroRider:
    - MCIL-8 connector
    - MCIL-4 connector
2. Connect the deck cable to the Windows PC:
    - USB connector (data transfer)
    - DB9 connector via the FTDI serial-to-USB converter (serial communication)

---

### 2. Configure the Communication Port

<photo>

1. Open **Device Manager**.
2. Expand **Ports (COM & LPT)**.
3. Record the COM port assigned to the FTDI serial adapter.
4. Open **Tera Term**.
5. Select the recorded COM port.
6. Configure the serial connection:

| Setting | Value |
|---------|------|
| Baud rate | 9600 |
| Data bits | 8 |
| Stop bits | 1 |
| Parity | None |

---

### 3. Start the Instrument

<photo>

1. Switch on the deck unit.
2. Allow approximately **60 seconds** for the instrument to complete its boot sequence.
3. Press any key within **10 seconds** to interrupt automatic data acquisition.

If data acquisition starts before you interrupt the boot sequence, press:

```text
Ctrl+C
```

to return to the command prompt.

!!! important "Boot sequence"

    If no text appears in Tera Term after approximately 60 seconds, switch off the deck unit, disconnect the cables and repeat the procedure from Step 1.

---

### 4. Verify the Instrument Configuration

1. List the contents of the data directory.

```text
dir data
```

Record the name and timestamp of the most recent data file.

2. Display the instrument configuration.

```text
type setup.cfg
```

Verify the configuration and probe serial numbers if required.

---

### 5. Run the Calibration Test

Run the calibration routine.

```text
odas5ir -c all
```

Save the terminal output for future reference if required.

---

### 6. Run the Bench Test

Start a 60-second bench test.

```text
odas5ir -f setup.cfg -l 3000 -t 60
```

Allow the test to continue for approximately **5 minutes** to collect multiple sample records.

Press:

```text
Ctrl+C
```

to stop data acquisition.

---

### 7. Verify Test Data

List the contents of the data directory again.

```text
dir data
```

Confirm that one or more new data files have been created.

Record the filename of the latest file.

---

### 8. Download the Test Data

Switch the instrument into USB transfer mode.

```text
usbl
```

1. Open **RSILink**.
2. Select the COM port associated with the USB download connection.
3. Click **Get Root Directory**.
4. Open the **Data** directory.
5. Select all newly created files.
6. Click **Download**.

---

### 9. Exit USB Transfer Mode

1. Close **RSILink**.
2. Return to **Tera Term**.
3. Exit USB transfer mode.

```text
q
```

4. Switch off the deck unit.
5. Disconnect the deck cable from the MicroRider.

## Commands Used

| Command | Description |
|---------|-------------|
| `dir data` | List data files |
| `type setup.cfg` | Display instrument configuration |
| `odas5ir -c all` | Run calibration test |
| `odas5ir -f setup.cfg -l 3000 -t 60` | Run bench test |
| `usbl` | Enter USB transfer mode |
| `q` | Exit USB transfer mode |

## Final Check

- [ ] Instrument communication verified.
- [ ] Instrument configuration reviewed.
- [ ] Calibration completed.
- [ ] Bench test completed successfully.
- [ ] Test data downloaded.
- [ ] Instrument powered off.
- [ ] Deck cable disconnected.