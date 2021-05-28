---
title: "Bikin \"pomodoro timer\" dengan Python"
date: 2021-05-28T16:59:06+08:00
---

Kali ini aku membuat pomodoro timer menggunakan bahasa Python. Jadi idenya, programnya berisi hitungan mundur selama 25 menit. Ketika waktunya habis, akan ditampilkan tulisan "Done!" yang menandakan programnya telah berhenti. Dan jika ingin memulai hitungan mundurnya lagi, sisa mulai ulang programnya.

Programnya berbasis Command Line.

## Source Code

```py
import time


def printTime(seconds):
    minutes = seconds // 60
    seconds = seconds - (minutes * 60)
    minutes = str(minutes).zfill(2)
    seconds = str(seconds).zfill(2)
    print(f'{minutes}:{seconds}')


def startCountdown(seconds):
    printTime(seconds)

    while(seconds > 1):
        time.sleep(1)
        seconds -= 1
        printTime(seconds)
    else:
        time.sleep(1)
        print('Done!')


startCountdown(1500)
```