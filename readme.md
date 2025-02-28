# Cipher Decoder Ring PCB

The Cipher Decoder Ring is a toy (not designed for professional use) that allows users to encrypt/decrypt messages using a rotary encoder and LED-guided interface (No screen, or computer required). This toy uses a modern [streaming encryption algorithm](https://en.wikipedia.org/wiki/Stream_cipher) [ChaCha20](https://en.wikipedia.org/wiki/Salsa20#ChaCha_variant) ([RFC7539](https://datatracker.ietf.org/doc/html/rfc7539)) that as of the year 2025 is considered strong encryption (OverKill). A 3D printed dial is fitted over the rotary encoder shaft to mimic a combination lock.

As a backup, when the [RP2040](https://www.raspberrypi.com/products/rp2040/) is connected via USB to a PC, it enumerates as a serial terminal (115200 Baud 8-N-1). A user then could send encoded or decoded messages directly to the serial terminal instead of entering them using the rotary encoder.

Created by: [Steven Smethurst](https://blog.abluestar.com/about) (@funvill)

**!!! Design has not been tested, Sent to manufacturing on 2024-Feb-27 !!!**

## Key Features

- **Stateless Encryption** – No stored keys, no stored state. If this device is captured it can't be used to decode existing encrypted messages.
- **User-Defined Seed & Nonce** – Entered via the rotary encoder for ChaCha20 encryption.
- **Multiple Encryption Modes** – Select from ChaCha20, AES-GCM, ROT13, and more.
- **USB-C Interface** – No battery, and serial interface for encoding binary data.

## How it works

### Step 1 - Select "Encrypt" or "Decrypt"

When the device is powered on

The "Encrypt" LED starts to blink. The user can rotate the dial left or right to switch between "Encrypt" or "Decrypt" mode. When the user has selected the option that they want, they push the dial to confirm their selection.

### Step 2 - Enter seed phase

The "Mode" LED turns red. This indicates that the user can enter a seed phase using the dial. Single click on the dial selects the letter used in the seed phase. A long press on the dial confirms the seed phase is and moves on to the next phase.

### Step 3 - Enter messages

The "Mode" LED turns green. The user can enter the message using the dial one letter at a time. After each letter has been entered the corresponding encoded letter will turn blue. The user writes down the blue letters to encode or decode the message.

## Project Goals

The goal of this project was to learn about [Streaming Cipher](https://en.wikipedia.org/wiki/Stream_cipher) such as [ChaCha20](https://en.wikipedia.org/wiki/Salsa20#ChaCha_variant) as well as making a toy or giveaway for conventions like Hackaday's [SuperCon](https://hackaday.io/superconference/), and Supplyframe's [Teardown](https://www.crowdsupply.com/teardown/).

A secondary goal is to be able to manufacture this board for less then $10 CAD using [JLCPCB](https://jlcpcb.com/) (No manual soldering)

## Technical Specifications

- [Seeed Studio XIAO RP2040](https://wiki.seeedstudio.com/XIAO-RP2040/) microprocessor with USB-C
- [XL-1615RGBC-WS2812B](https://jlcpcb.com/partdetail/XINGLIGHT-XL_1615RGBCWS2812B/C5349954) Individually addressable LEDs
- [EC11E09244BS](https://tech.alpsalpine.com/e/products/detail/EC11E09244BS/) Rotary Encoder

## Tools used

- [KiCad v9.0](https://www.kicad.org/) - EDA
- [EasyEDA2Kicad](https://github.com/uPesy/easyeda2kicad.py) - Converts JLCPCB parts to KiCad files.
- [Gingerbread](https://gingerbread.wntr.dev/index.html) - Converts SVG or Affinity Designer files to KiCad files.

## Preview

### Front

![Preview-front](https://github.com/funvill/cipher-decoder-ring-pcb/blob/main/preview-front.png?raw=true)

### Back

![Preview-back](https://github.com/funvill/cipher-decoder-ring-pcb/blob/main/preview-back.png?raw=true)

### Schematic

![Preview-back](https://github.com/funvill/cipher-decoder-ring-pcb/blob/main/preview-schematic.png?raw=true)
