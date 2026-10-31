# Threat Model

**Scope:** VL53L9 person detection on NUCLEO-N657X0-Q + STEVAL-VL53L9. Two-person course project, dev board, lab use only. The dataset contains only the two authors, who consent to its use. The device holds no credentials and has no network connection.

Response levels: **basic hygiene** < **software encryption** < **hardware locks**.

## 1. Depth recordings of the authors (user data)
- **Asset:** body shape and movement data of two identifiable people.
- **Threat / attack surface:** no realistic attacker. The way in is accidental exposure: the git repo made public, or files shared beyond the course.
- **Response: basic hygiene.** Don't push model data into the public repo. Encryption is not needed as the data is low-resolution depth of two consenting authors, so the only meaningful harm is unwanted publication, and access control prevents that.

## 2. Firmware and model weights (model IP)
- **Asset:** the firmware image and the trained model on external xSPI flash.
- **Threat / attack surface:** at most a curious visitor in the lab. The ways in are the open SWD/ST-LINK port, reading the external flash chip, and the unauthenticated UART capture channel. All of them require physical access.
- **Response: basic hygiene:** Keep the board with the autors. The model has little value outside this project and no one realistic wants it. If it would be productized, the requirements become authenticated boot, a debug lock (hardware locks) and OTFDEC flash encryption.