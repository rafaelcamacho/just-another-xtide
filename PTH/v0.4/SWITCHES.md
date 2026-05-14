# Switch and Jumper Configuration

This document describes the configuration switches and jumpers available on the Just Another XT-IDE PTH v0.4 board.

---

## Switch Logic

| Value | State |
|-------|-------|
| 0 | OFF |
| 1 | ON |

---

# IDE Address

Default setting: `110000` (`0x300h`)

The IDE I/O base address is configured through switches 1 to 6.

| Switch | Address Bit |
|--------|-------------|
| 1 | A9 |
| 2 | A8 |
| 3 | A7 |
| 4 | A6 |
| 5 | A5 |
| 6 | A4 |

---

## Address Table

| 1 | 2 | 3 | 4 | 5 | 6 | Address |
|---|---|---|---|---|---|---------|
| 1 | 0 | 0 | 0 | 0 | 0 | 0200h |
| 1 | 0 | 0 | 0 | 0 | 1 | 0210h |
| 1 | 0 | 0 | 0 | 1 | 0 | 0220h |
| 1 | 0 | 0 | 0 | 1 | 1 | 0230h |
| 1 | 0 | 0 | 1 | 0 | 0 | 0240h |
| 1 | 0 | 0 | 1 | 0 | 1 | 0250h |
| 1 | 0 | 0 | 1 | 1 | 0 | 0260h |
| 1 | 0 | 0 | 1 | 1 | 1 | 0270h |
| 1 | 0 | 1 | 0 | 0 | 0 | 0280h |
| 1 | 0 | 1 | 0 | 0 | 1 | 0290h |
| 1 | 0 | 1 | 0 | 1 | 0 | 02A0h |
| 1 | 0 | 1 | 0 | 1 | 1 | 02B0h |
| 1 | 0 | 1 | 1 | 0 | 0 | 02C0h |
| 1 | 0 | 1 | 1 | 0 | 1 | 02D0h |
| 1 | 0 | 1 | 1 | 1 | 0 | 02E0h |
| 1 | 0 | 1 | 1 | 1 | 1 | 02F0h |
| 1 | 1 | 0 | 0 | 0 | 0 | 0300h |
| 1 | 1 | 0 | 0 | 0 | 1 | 0310h |
| 1 | 1 | 0 | 0 | 1 | 0 | 0320h |
| 1 | 1 | 0 | 0 | 1 | 1 | 0330h |
| 1 | 1 | 0 | 1 | 0 | 0 | 0340h |
| 1 | 1 | 0 | 1 | 0 | 1 | 0350h |
| 1 | 1 | 0 | 1 | 1 | 0 | 0360h |
| 1 | 1 | 0 | 1 | 1 | 1 | 0370h |
| 1 | 1 | 1 | 0 | 0 | 0 | 0380h |
| 1 | 1 | 1 | 0 | 0 | 1 | 0390h |
| 1 | 1 | 1 | 0 | 1 | 0 | 03A0h |
| 1 | 1 | 1 | 0 | 1 | 1 | 03B0h |
| 1 | 1 | 1 | 1 | 0 | 0 | 03C0h |
| 1 | 1 | 1 | 1 | 0 | 1 | 03D0h |
| 1 | 1 | 1 | 1 | 1 | 0 | 03E0h |
| 1 | 1 | 1 | 1 | 1 | 1 | 03F0h |

---

## Notes

- The most common XT-IDE address is `0300h`.
- Avoid conflicts with serial, parallel, network and sound cards.
- Some BIOS configurations may expect the controller at `0300h`.

---

# ROM Options

Default setting: `10001111` (`D0000h`,`32k`,`ROM Enabled`,`Writable`)

Switches 1 to 4 define the ROM base memory address.

| Switch | Address Bit |
|--------|-------------|
| 1 | A16 |
| 2 | A15 |
| 3 | A14 |
| 4 | A13 |

---

## Address Table

| 1 | 2 | 3 | 4 | Address | ROM Support |
|---|---|---|---|----------|--------------|
| 0 | 0 | 0 | 0 | C0000h | All |
| 0 | 0 | 0 | 1 | C2000h | 8k  |
| 0 | 0 | 1 | 0 | C4000h | 816k |
| 0 | 0 | 1 | 1 | C6000h | 8k |
| 0 | 1 | 0 | 0 | C8000h | All |
| 0 | 1 | 0 | 1 | CA000h | 8k |
| 0 | 1 | 1 | 0 | CC000h | 816k |
| 0 | 1 | 1 | 1 | CE000h | 8k |
| 1 | 0 | 0 | 0 | D0000h | All |
| 1 | 0 | 0 | 1 | D2000h | 8k |
| 1 | 0 | 1 | 0 | D4000h | 816k |
| 1 | 0 | 1 | 1 | D6000h | 8k |
| 1 | 1 | 0 | 0 | D8000h | All |
| 1 | 1 | 0 | 1 | DA000h | 8k |
| 1 | 1 | 1 | 0 | DC000h | 816k |
| 1 | 1 | 1 | 1 | DE000h | 8k |

---

## ROM Support Notes

| Description | Meaning |
|-------------|---------|
| All | All ROM sizes, compatible with 8k, 16k and 32k ROMs |
| 8k | 8k only, valid only for 8k ROM configurations |
| 816k | Compatible with both 8k and 16k ROMs |

---

# ROM Size Selection

Switches 5 and 6 define the ROM size.

| 5 | 6 | ROM Size |
|---|---|-----------|
| 0 | 0 | 8k |
| 1 | 0 | 16k |
| 1 | 1 | 32k |

---

# ROM Control

Switches 7 and 8 control EEPROM enable and write protection.

| 7 | 8 | Function |
|---|---|----------|
| EN | WR | EEPROM Enable / Write Control |

## Typical Settings

| EN | WR | Description |
|----|----|-------------|
| 0 | 0 | ROM disabled |
| 1 | 0 | ROM enabled, write protected |
| 1 | 1 | ROM enabled, write enabled |

---

## Notes

- `C8000h` and `D0000h` are the most common XT-IDE ROM addresses.
- Avoid ROM address conflicts with VGA, network and SCSI cards.
- Write enable should only be activated during EEPROM programming.
- 32k ROMs require aligned address ranges marked as "All ROM sizes".

---

# HiSpeed

The `HiSpeed` switch control the HiSpeed operating mode of the controller.

| HiSpeed | Mode |
|----|------|
| OFF | XT-IDE Rev1 Compatible mode |
| ON | XT-IDE Rev2 HiSpeed mode |

## Important

Changing the `HiSpeed` setting requires:

1. Reconfiguring the XTIDE Universal BIOS using `XTIDECFG.COM`, under Controller Type.
2. Reflashing the EEPROM with the updated BIOS image

Failure to update the BIOS configuration may prevent proper controller operation.

---

# IDE +5V Pin 20

A dedicated jumper allows +5V power to be supplied through pin 20 of the IDE connector.

## Usage

Enable this jumper when using:

- Disk-on-Module (DoM) devices.
- CompactFlash IDE adapters.
- Other IDE devices requiring power from pin 20.

Disable the jumper when using:

- Standard IDE hard drives with external power.
- Devices that do not expect +5V on pin 20.

---

# Operational Notes

## ROM Enable

Disable the ROM (`ROM Options`, switch 7 OFF) if the current ROM configuration prevents the system from booting.

For ROM reprogramming under DOS:

1. Boot the system with ROM disabled.
2. Enable switch 7 after the system is running.
3. Reflash the ROM.

Supported EEPROMs:

- 28C64
- 28C256

---

## ROM Write Protection

Disable ROM writes (`ROM Options`, switch 8 OFF) once the system is operating correctly.

This prevents accidental ROM overwrites.

---

## ROM Address Priority

Ensure the XT-IDE BIOS ROM address is located above any other boot ROMs installed in the system.

Otherwise:

- IDE drives may still be detected.
- Booting from those drives may fail.

---

## IDE Address Changes

Changing the IDE I/O address requires:

1. Reconfiguring the BIOS using `XTIDECFG.COM`.
2. Reflashing the ROM.

Changing only the ROM address does not require BIOS modification.

---

## IBM XT Slot 8 Usage

When using the board in slot 8 of an IBM XT system, verify the assembly instructions carefully.

Some IBM XT systems have slot-specific limitations and signal differences.

---

## IRQ Usage

IRQ is not used by XTIDE Universal BIOS versions released since October 2020.

The controller operates entirely in polling mode.
