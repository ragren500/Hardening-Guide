# Server Hardening för macOS     

**OBS** Denna guide är under utveckling och uppdateras löpande!

## Introduktion

Serverhärdning ("Hardening") innebär att säkra en server för att minimera risken för angrepp. Det inkluderar att täppa till sårbarheter, begränsa åtkomst och implementera säkerhetsprinciper.

## MacOS Hardening Guide

Denna sektion innehåller säkerhetsåtgärder för att härda macOS och skydda det mot olika hot.

## 1. Installera en ren kopia av macOS
Varför: För att starta med en säker konfiguration utan tidigare fel eller skadlig kod. 

## 2. Uppdatera macOS regelbundet
Varför: För att säkerställa att systemet alltid är skyddat mot de senaste säkerhetshoten.

Hur? Öppna Terminalen och kör följande kommando:
```bash
sudo softwareupdate --install --all
```

## 3. Aktivera automatiska uppdateringar
Varför: För att undvika manuella uppdateringar och hålla systemet uppdaterat automatiskt.

## 4. Aktivera brandvägg
Varför: För att blockera obehörig nätverkstrafik och minska attackytan.

Hur? Öppna Terminalen och kör följande kommando:
```bash
sudo /usr/libexec/ApplicationFirewall/socketfilterfw --setglobalstate on
```

## 5. Inaktivera automatiska inloggningar
Varför: För att hindra obehöriga från att logga in utan lösenord.

## 6. Aktivera FileVault för disk-kryptering
Varför: För att skydda känslig data från att läsas vid fysisk åtkomst till datorn.

Hur? Öppna Terminalen och kör följande kommando:
```bash
sudo fdesetup enable
```

## 7. Begränsa tjänster och delning
Varför: För att minimera antalet öppna portar och minska risken för fjärrangrepp.

## 8. Förhindra osignerad programvara
Varför: För att minska risken för skadlig kod genom att endast tillåta verifierade appar.

## 9. Säkerställ att Gatekeeper är aktiverad
Varför: För att blockera och varna för okända eller osignerade program.

Hur? Öppna Terminalen och kör följande kommando:
```bash
sudo spctl --master-enable
```

## 10. Aktivera XProtect och MRT
Varför: För att dra nytta av Apples inbyggda skydd mot skadlig kod.

Hur? Öppna Terminalen och kör följande kommando:
```bash
sudo softwareupdate --background-critical
```

## 11. Använd en lösenordshanterare
Varför: För att generera och lagra starka lösenord på ett säkert sätt.

## 12. Begränsa sudo-användning
Varför: För att förhindra att obehöriga kan eskalera privilegier och utnyttja sudo under en längre tid.

Hur? Öppna Terminalen och kör följande kommando:
```bash
echo 'Defaults timestamp_timeout=5' | sudo tee -a /etc/sudoers
```

## 13. Aktivera systemintegritetsskydd (SIP)
Varför: För att skydda viktiga systemfiler från ändringar.

Hur? Öppna Terminalen och kör följande kommando:
```bash
csrutil status
csrutil enable
```

## 14. Stäng av fjärrinloggning (SSH om det inte behövs)
Varför: För att minska attackytan och förhindra obehörig fjärråtkomst.

Hur? Öppna Terminalen och kör följande kommando:
```bash
sudo systemsetup -setremotelogin off
```

## 15. Begränsa vilka appar som kan köra skript och automation
Varför: För att minimera risken att skadlig programvara kan exekvera skript.

## 16. Inaktivera Bluetooth när det inte används
Varför: För att minska attackytan för trådlösa attacker.

Hur? Öppna Terminalen och kör följande kommando:
```bash
sudo defaults write /Library/Preferences/com.apple.Bluetooth ControllerPowerState -int 0
```

## 17. Övervaka systemloggar och säkerhetshändelser
Varför: För att identifiera misstänkt aktivitet och potentiella angrepp.

Hur? Öppna Terminalen och kör följande kommando:
```bash
log show --predicate 'eventMessage contains "failed"' --last 24h
```

## 18. Förhindra Safari från att öppna nedladdningar automatiskt
Varför: För att minimera risken att skadlig kod körs vid nedladdning.

## 19. Visa filändelser i Finder
Varför: För att tydligt identifiera filformat och undvika dolda skadliga filer.

## 20. Ställ in en striktare skärmlåsningspolicy
Varför: För att skydda systemet vid inaktivitet.

Hur? Öppna Terminalen och kör följande kommando:
```bash
defaults write com.apple.screensaver idleTime -int 300
```

## 21. Använd ett standardkonto istället för administratörskonto
Varför: För att minska risken att skadlig kod körs med admin-behörighet.

## 22. Inaktivera iCloud Drive om det inte behövs
Varför: För att minska risken att filer exponeras via molnsynkronisering.

Hur? Öppna Terminalen och kör följande kommando:
```bash
defaults write NSGlobalDomain NSDocumentSaveNewDocumentsToCloud -bool false
```

## 23. Begränsa mikrofon- och kameråtkomst
Varför: För att förhindra att appar kan avlyssna och spela in utan tillstånd.

## 24. Inaktivera Wi-Fi när det inte används
Varför: För att minska risken för obehörig nätverksåtkomst.

Hur? Öppna Terminalen och kör följande kommando:
```bash
networksetup -setairportpower en0 off
```

## 25. Kontrollera och inaktivera osäkra Kernel Extensions
Varför: För att eliminera äldre sårbara drivrutiner.

Hur? Öppna Terminalen och kör följande kommando:
```bash
kmutil inspect
```

## 26. Använd en DNS-tjänst med skydd
Varför: För att skydda mot skadliga webbplatser och phishing-attacker.

Hur? Öppna Terminalen och kör följande kommando:
```bash
networksetup -setdnsservers Wi-Fi 1.1.1.1 1.0.0.1
```

## 27. Skanna och ta bort skadlig programvara
Varför: För att identifiera och ta bort eventuell malware.

Hur? Det finns inga inbyggda kommandoradsverktyg i macOS för fullständig malware-skanning, men här är ett tips:

#### Använd Malwarebytes (gratis & lätt att använda)
	1.	Gå till: https://www.malwarebytes.com/mac
	2.	Ladda ner och installera
	3.	Kör en genomsökning
	4.	Följ anvisningarna för att ta bort skadlig kod

Malwarebytes är pålitligt och hittar mycket som andra program missar.

## 28. Granska webbläsartillägg
Varför: För att minska risken för att skadliga tillägg får åtkomst till känsliga data.

Hur? Gå igenom installerade tillägg i varje webbläsare du använder och ta bort de du inte behöver eller inte litar på:

#### Safari
	1.	Öppna Safari
	2.	Gå till Inställningar > Tillägg
	3.	Granska listan och klicka på Avinstallera eller Stäng av för tillägg du inte vill ha

#### Google Chrome
	1.	Öppna Chrome
	2.	Gå till chrome://extensions/
	3.	Inaktivera eller ta bort tillägg genom att klicka på reglaget eller Ta bort

 #### Firefox
	1.	Öppna Firefox
	2.	Gå till about:addons
	3.	Klicka på Tillägg i menyn och välj att inaktivera eller ta bort

## 29. Använd en utgående brandvägg
Varför: För att blockera oönskad nätverkstrafik från systemet.

Hur? 
macOS inbyggda brandvägg hanterar inkommande trafik. För utgående trafik behöver du ett tredjepartsprogram.
Ett populärt alternativ är:

#### LuLu (gratis & open source)
	1.	Gå till: https://objective-see.org/products/lulu.html
	2.	Ladda ner och installera
	3.	När du kör ett program första gången kommer LuLu att fråga om det ska få tillgång till nätverket
	4.	Du kan tillåta eller blockera enligt principen: whitelist as needed

## 30. Blockera skadliga domäner via /etc/hosts
Varför: För att minska risken för nätfiske och skadliga domäner.

Hur? Öppna Terminalen och kör följande kommando:

#### 1.Redigera hosts-filen med t.ex. nano:

```bash
sudo nano /etc/hosts
```

#### 2. Lägg till rader längst ner för att blockera domäner, t.ex.:

```bash
0.0.0.0 malicious-domain.com
0.0.0.0 ads.badsite.net
```

#### 3. Spara (Ctrl + O) och stäng (Ctrl + X)

#### 4. Töm DNS-cache:

```bash
sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder
```

## 31. Aktivera säker tangentbordsinmatning i Terminal
Varför: För att förhindra att andra appar registrerar tangenttryckningar.

Hur?

	1.	Öppna Terminal
	2.	Gå till menyn: Terminal > Inställningar
	3.	Välj din profil (t.ex. “Standard”)
	4.	Under fliken Tangentbord, se till att alternativet “Aktivera säker tangentbordsinmatning” är ikryssat
 
Detta gör att andra appar inte kan läsa dina tangenttryckningar när du skriver i Terminalen.

## 32. Aktivera binär allowlisting med Google Santa
Varför: För att stoppa obehöriga program från att köras.

Hur?

	1.	Gå in på: https://santa.dev
	2.	Följ installationsinstruktionerna där (Santa körs som en bakgrundsagent)
	3.	Du kan köra i Monitor Mode (övervakning) eller Lockdown Mode (blockerar allt utom whitelistas)
	4.	Hantera regler med santactl, t.ex.:
	
 Öppna terminalen och kör:
 ```bash
sudo santactl rule --whitelist --path /Applications/SäkerApp.app
```

## 33. Inaktivera AirDrop om det inte behövs
Varför: För att förhindra att obehöriga skickar filer till enheten.

Hur? Öppna Terminalen och kör följande kommando:
```bash
defaults write com.apple.airdrop disable -bool true
```

## 34. Inaktivera Gästkontot
Varför: För att förhindra obehöriga från att logga in utan lösenord.

Hur? Öppna Terminalen och kör följande kommando:
```bash
sudo defaults write /Library/Preferences/com.apple.loginwindow GuestEnabled -bool false
```

## 35. Blockera onödiga portar med en anpassad brandväggsregel
Varför: För att minska attackytan och begränsa obehörig nätverkstrafik.

Hur? Öppna Terminalen och kör följande kommando:
```bash
sudo /usr/libexec/ApplicationFirewall/socketfilterfw --setblockall on
```
