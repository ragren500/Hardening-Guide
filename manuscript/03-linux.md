# Gör din Linux-server säkrare – Enkla steg
** Obs! Denna guide uppdateras då och då.**

## Vad är detta?
Att göra en Linux-server säkrare betyder att skydda den från hackare och andra hot. Man stänger säkerhetshål och gör det svårare för någon att ta sig in.

## Så här gör du din Linux-server tryggare
Här är enkla saker du kan göra för att förbättra säkerheten.

### 1. Installera Linux från början
**Varför?** Då vet du att systemet är rent och inte har gamla fel eller virus.

### 2. Uppdatera systemet ofta
**Varför?** Nya uppdateringar lagar säkerhetshål.
```bash
sudo apt update && sudo apt upgrade -y   
sudo dnf update -y
```

### 3. Slå på automatisk uppdatering
**Varför?** Då sköter sig uppdateringarna själva.
```bash
sudo systemctl enable --now unattended-upgrades
```

### 4. Starta brandväggen
**Varför?** Den stoppar farlig trafik utifrån.
```bash
sudo ufw enable
sudo firewall-cmd --permanent --add-service=ssh
sudo firewall-cmd --reload
```

### 5. Stoppa root-inloggning via SSH
**Varför?** Det gör det svårare för någon att gissa sig in som administratör.
```bash
sudo sed -i 's/^PermitRootLogin yes/PermitRootLogin no/' /etc/ssh/sshd_config
sudo systemctl restart sshd
```

### 6. Använd SSH-nyckel istället för lösenord
**Varför?** Det är mycket säkrare än lösenord.
```bash
mkdir -p ~/.ssh && chmod 700 ~/.ssh
echo "DIN_SSH_NYCKEL_HÄR" >> ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
```

### 7. Använd SELinux eller AppArmor
**Varför?** De bestämmer vad program får göra, vilket skyddar systemet.
```bash
sestatus         # För SELinux
sudo aa-status   # För AppArmor
```

### 8. Begränsa användare med sudo
**Varför?** Bara betrodda personer ska kunna göra viktiga ändringar.
```bash
sudo visudo
```

### 9. Stäng av onödiga tjänster
**Varför?** Ju färre saker som körs, desto mindre risk.
```bash
sudo systemctl list-unit-files --type=service --state=enabled
sudo systemctl disable tjänstnamn --now
```

### 10. Titta på loggar
**Varför?** Där kan du se om någon försöker ta sig in.
```bash
sudo journalctl -xe
sudo cat /var/log/auth.log | grep "Failed password"
```

### 11. Sök efter virus
**Varför?** För att hitta och ta bort skadlig kod.
```bash
sudo apt install clamav -y
clamscan -r /home
```

### 12. Blockera farliga hemsidor
**Varför?** För att hindra systemet från att gå till skadliga sidor.
```bash
echo "0.0.0.0 badwebsite.com" | sudo tee -a /etc/hosts
```

### 13. Begränsa vad som får skickas ut
**Varför?** Så att ingen kan skicka ut stulen information.
```bash
sudo ufw default deny outgoing
```

### 14. Stäng av USB-portar (om du inte behöver dem)
**Varför?** Skyddar mot fysiska attacker via USB-minnen.
```bash
echo "blacklist usb-storage" | sudo tee -a /etc/modprobe.d/blacklist.conf
sudo update-initramfs -u
```

### 15. Använd lösenordshanterare
**Varför?** För att skapa och spara starka lösenord.
```bash
sudo apt install keepassxc -y
```

