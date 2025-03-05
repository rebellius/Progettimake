# Progettimake


-
--

🚗 Dashcam AI con Raspberry Pi: Un Progetto DIY per la Sicurezza Stradale 🎥🤖

Dopo settimane di sviluppo, sono felice di condividere il mio progetto: una Dashcam AI basata su Raspberry Pi 3 Model B e la Raspberry Pi AI Camera! 📷

🔧 Come funziona?

✅ Registra continuamente video di 10 secondi, eliminando quelli più vecchi per evitare di saturare la memoria.
✅ Analizza in tempo reale pedoni e veicoli per prevenire collisioni.
✅ Un sistema di LED segnala il livello di pericolo:
🟢 Verde = nessun pericolo
🟡 Giallo = attenzione
🔴 Rosso = pericolo imminente

🛠 Componenti e tecnologia usata:

Hardware:

Raspberry Pi 3 Model B

Raspberry Pi AI Camera

Modulo LED semaforico (rosso, giallo, verde)

Scheda microSD da almeno 50GB


Software:

OpenCV per il riconoscimento visivo

Python per la gestione della registrazione e analisi AI



🛠 Configurazione e installazione

1️⃣ Preparazione di Raspberry Pi:

Installare Raspberry Pi OS Lite e abilitare la fotocamera (sudo raspi-config).

Aggiornare il sistema:

sudo apt update && sudo apt upgrade -y

Installare le dipendenze:

sudo apt install python3-opencv python3-pip libcamera-apps -y
pip3 install numpy RPi.GPIO


2️⃣ Collegare l'hardware:

Fotocamera AI → connetterla alla porta CSI.

Modulo LED → collegare ai pin GPIO 17, 27 e 22 (più GND).


3️⃣ Scaricare ed eseguire lo script:

git clone https://github.com/tuo-repo/dashcam-ai.git
cd dashcam-ai
python3 dashcam.py

4️⃣ Avviare automaticamente lo script all’accensione:

Creare un servizio systemd:

sudo nano /etc/systemd/system/dashcam.service

Inserire:

[Unit]
Description=Dashcam AI
After=network.target

[Service]
ExecStart=/usr/bin/python3 /home/pi/dashcam-ai/dashcam.py
Restart=always
User=pi

[Install]
WantedBy=multi-user.target

Salvare e abilitare con:

sudo systemctl enable dashcam
sudo systemctl start dashcam


🚀 Obiettivo: rendere la sicurezza stradale più accessibile con un sistema low-cost basato su AI!

📢 Il codice sorgente sarà disponibile a breve! Se sei appassionato di elettronica, AI e automazione, fammi sapere cosa ne pensi! Idee e suggerimenti sono benvenuti!

#RaspberryPi #AI #ComputerVision #Dashcam #MachineLearning #IoT #ProgettoDIY


---

Puoi personalizzarlo aggiungendo il link al codice o immagini del progetto!

