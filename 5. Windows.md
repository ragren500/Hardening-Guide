# Server Hardening för Windows

## Introduktion


## 1. Uppdatera Windows och programvara

- **Automatiska uppdateringar**: Se till att automatiska uppdateringar är aktiverade för Windows så att säkerhetsuppdateringar installeras automatiskt.
- **Manuella uppdateringar**: Kontrollera regelbundet manuellt om det finns några tillgängliga uppdateringar i Windows Update.

Varför?

Regelbundna uppdateringar av Windows och programvara är en viktig del av att hålla din dator säker, effektiv och funktionell. De ger bättre prestanda, nya funktioner och skydd mot säkerhetshot, vilket gör att du kan utnyttja din utrustning på bästa möjliga sätt.



Hur? 

# Uppdatera Windows via Kommando

## Använd PowerShell

1. **Öppna PowerShell som administratör**:
   - Skriv "PowerShell" i Startmenyn.
   - Högerklicka på **Windows PowerShell** och välj **Kör som administratör**.

2. **Installera Windows Update-modulen** (om det inte redan är installerat):
   För att använda Windows Update-kommandon i PowerShell, måste du installera modulen `PSWindowsUpdate`:
   ```powershell
   Install-Module -Name PSWindowsUpdate

3. Sök efter uppdateringar: För att söka efter tillgängliga uppdateringar, kör följande kommando:
   
   Get-WindowsUpdate


4.  Installera uppdateringar: För att installera de tillgängliga uppdateringarna, använd detta kommando:
  
    Install-WindowsUpdate

5.  Starta om datorn efter installation (om det behövs): Om uppdateringar kräver en omstart för att slutföras, kör:
    
    Restart-Computer



2. Installera och använd antivirusprogram

- **Windows Defender**: Windows 10 och senare versioner kommer med Windows Defender, som är ett inbyggt antivirusprogram. Håll det aktiverat.
- **Tredjeparts antivirusprogram**: Om du föredrar ett tredjeparts antivirusprogram, se till att det är uppdaterat och konfigurerat för att ge skydd i realtid.

Varför?

Användning av antivirusprogram ger ett kraftfullt försvar mot skadlig programvara och cyberhot som kan skada din dator, stjäla din information eller påverka din integritet. Genom att ha ett antivirusprogram installerat kan du känna dig tryggare när du surfar på nätet, gör bankärenden, laddar ner filer eller använder din dator för andra aktiviteter.



Hur?

Installera Antivirusprogram via Kommando

Installera Windows Defender Antivirus (Inbyggt i Windows)

Windows Defender är inbyggt i Windows och aktiveras automatiskt, men om du vill säkerställa att det är aktiverat och uppdaterat kan du använda kommandon för att kontrollera och installera uppdateringar.

1. Kontrollera om Windows Defender är aktiverat**
   För att kontrollera om Windows Defender Antivirus är aktiverat, kör följande kommando i PowerShell:
     
   Get-MpPreference


   För att aktivera Windows Defender Antivirus, använd följande kommando:

   Set-MpPreference -DisableRealtimeMonitoring $false


   För att uppdatera virusdefinitionerna för Windows Defender, kör följande kommando:

   Update-MpSignature



3. Använd ett starkt lösenord och aktivera tvåfaktorsautentisering

- **Starka lösenord**: Se till att du använder ett komplext lösenord för dina användarkonton, gärna med en blandning av stora och små bokstäver, siffror och specialtecken.
- **Tvåfaktorsautentisering**: Aktivera tvåfaktorsautentisering (2FA) där det är möjligt för extra skydd, särskilt för Microsoft-kontot och andra tjänster som stöder det.

Varför?

Att använda ett starkt lösenord och aktivera tvåfaktorsautentisering är några av de mest effektiva sätten att skydda dina onlinekonton och personlig information. Starka lösenord minskar risken för att någon ska kunna gissa sig till ditt lösenord, medan 2FA ger ett extra lager av skydd mot alla typer av attacker, inklusive phishing och lösenordsstölder. Genom att använda dessa metoder säkerställer du att din information är bättre skyddad och minskar risken för att bli utsatt för cyberbrott.

Hur?

Steg:
Logga in på ditt Microsoft-konto: Gå till Microsoft-kontots säkerhetsinställningar.

Aktivera tvåfaktorsautentisering:

Välj Tvåstegsverifiering under säkerhetsinställningarna.

Följ instruktionerna:

Microsoft guidar dig genom processen för att aktivera 2FA via Authenticator-appen eller SMS.

Verifikation:

Bekräfta din valda autentiseringsmetod genom att ange den kod som skickas till dig.



 4. Aktivera Brandvägg

- **Windows-brandvägg**: Se till att Windows-brandväggen är aktiverad. Den kan blockera oönskad trafik och förhindra att skadlig programvara kommunicerar med externa servrar.

Varför?

Att aktivera brandväggen är en viktig och grundläggande säkerhetsåtgärd för att skydda din dator, nätverk och privata information från obehörig åtkomst, virus, skadlig programvara och andra cyberhot. Den fungerar som ett första försvarslinje som blockerar skadlig trafik och förebygger många typer av attacker, vilket gör det svårare för angripare att komma åt dina data.


Hur?

För att aktivera brandväggen för alla profiler, kör detta kommando:

Set-NetFirewallProfile -All -Enabled True

För att aktivera brandväggen för en viss profil, exempelvis Privat, använd:

Set-NetFirewallProfile -Profile Private -Enabled True

För att bekräfta att brandväggen är aktiverad, kör följande kommando:

Get-NetFirewallProfile | Format-Table Name, Enabled



## 5. Säkerhetskopiera dina data

- **Regelbundna säkerhetskopior**: Använd Windows inbyggda verktyg för att skapa säkerhetskopior, till exempel `Historik för filer` eller `Windows Backup`. Detta kan hjälpa dig att återställa viktiga data om systemet blir infekterat eller skadas.
- **Extern lagring eller molnlagring**: Säkerhetskopiera data både lokalt (t.ex. extern hårddisk) och till molnlagringstjänster.

Varför?

Säkerhetskopiering är en enkel men mycket viktig åtgärd för att skydda dina filer och data. Oavsett om det handlar om att skydda mot hårdvarufel, skadlig programvara, oavsiktlig radering eller fysiska katastrofer, ger en säkerhetskopia dig tryggheten att du kan återställa din data och minimera konsekvenserna av oförutsedda händelser. Genom att regelbundet säkerhetskopiera dina filer kan du säkerställa att du inte riskerar att förlora viktig information som kan vara svår eller omöjlig att återskapa.



Hur?

# Hur Man Säkerhetskopierar Filer på Windows

## 1. Säkerhetskopiera med Windows Backup (Historik)
- Gå till **Inställningar** > **Uppdatering och Säkerhet** > **Säkerhetskopiering**.
- Välj **Lägg till en enhet** och aktivera **Automatiskt säkerhetskopiera mina filer**.

## 2. Säkerhetskopiera med File History
- Öppna **Kontrollpanelen** > **System och Säkerhet** > **File History**.
- Klicka på **Slå på File History** och välj en extern enhet för säkerhetskopiering.

## 3. Säkerhetskopiera med Manuell Kopiering till Extern Enhet
- Kopiera filer manuellt från din dator till en extern hårddisk eller USB-enhet.

## 4. Säkerhetskopiera till Molnlagring (t.ex. OneDrive)
- Installera **OneDrive** och logga in med ditt Microsoft-konto.
- Flytta de filer du vill säkerhetskopiera till OneDrive-mappen på din dator.

## 5. Säkerhetskopiera med Tredjepartsprogram (t.ex. Acronis True Image)
- Ladda ner och installera tredjepartsprogram för att skapa mer avancerade säkerhetskopior.



## 6. Hantera användarbehörigheter

- **Begränsade konton**: Använd standardanvändarkonton för alla användare istället för administratörskonton för att minska risken för oavsiktlig skadlig aktivitet.
- **UAC (User Account Control)**: Se till att UAC är aktiverat för att varna dig när program försöker göra ändringar på din dator.

Varför?

Att hantera användarbehörigheter är en viktig del av att upprätthålla både datasäkerhet och integritet i alla typer av system och nätverk. Genom att noggrant definiera och begränsa åtkomst kan du skydda känslig information, förhindra obehörig åtkomst, minimera riskerna för användarfel och följa relevanta regler och föreskrifter. Det skapar också en tryggare och mer kontrollerad miljö där endast auktoriserade personer kan påverka kritiska system och data.

Hur?

Skapa användare: net user användarnamn lösenord /add

Ta bort användare: net user användarnamn /delete

Ändra lösenord: net user användarnamn nyttlösenord

Lägg till användare i grupp: net localgroup gruppnamn användarnamn /add

Ge filbehörigheter: icacls "C:\sökväg\till\fil" /grant användarnamn:behörighet

Ta bort filbehörigheter: icacls "C:\sökväg\till\fil" /remove användarnamn



## 7. Aktivera BitLocker för att kryptera din disk

- **BitLocker**: Aktivera BitLocker-kryptering på din systemdisk för att skydda data mot obehörig åtkomst om datorn stjäls eller om den används på en annan enhet.
- **Kryptera externa enheter**: Kryptera externa diskar och USB-enheter med BitLocker eller annan krypteringsteknik.

Varför?

Att aktivera BitLocker och kryptera din disk ger ett starkt skydd för din data, oavsett om du använder din enhet privat eller i en företagsmiljö. Det skyddar mot stöld, förlust, obehörig åtkomst och skadlig programvara, samtidigt som det säkerställer att din information är säker och konfidentiell. Det är ett enkelt och effektivt sätt att stärka säkerheten för dina enheter och följa säkerhetsregler och riktlinjer.

Hur?

Kontrollera status: manage-bde -status

Aktivera BitLocker: manage-bde -on C: -RecoveryPassword

Kontrollera krypteringsstatus: manage-bde -status C:

Spara återställningsnyckel: manage-bde -protectors -add C: -RecoveryPassword -RecoveryKey F:

Deaktivera BitLocker: manage-bde -off C:



## 8. Installera endast betrodda program

- **Ladda ned program från officiella källor**: Installera endast program och appar från betrodda och officiella källor, till exempel Microsoft Store eller direkt från programvarutillverkarens webbplats.
- **Kontrollera signaturer**: Använd digitala signaturer för att verifiera äktheten hos programvara och filer.

Varför?

Att endast installera betrodda program är en av de enklaste och mest effektiva säkerhetsåtgärderna för att skydda din dator och dina data. Genom att följa detta råd minskar du risken för att drabbas av skadlig programvara, stöld av personlig information, systeminstabilitet och andra säkerhetsproblem. Det hjälper också till att säkerställa att din programvara är laglig, uppdaterad och fri från oönskade komponenter. Genom att vara noggrann med var du hämtar dina program, kan du skapa en mycket säkrare och stabil digital miljö.



Hur?

# Installera Endast Betrodda Program på Windows

## 1. Aktivera Windows Defender SmartScreen
- Gå till **Inställningar** > **Sekretess och säkerhet** > **Windows-säkerhet** > **App och webbintegritet**.
- Under **SmartScreen för appar och filer**, välj **Varna för appar och filer från okända källor**.

## 2. Använd "Endast betrodda appar" i Windows
- Gå till **Inställningar** > **Appar** > **Appinstallation**.
- Välj **Microsoft Store endast**.

## 3. Aktivera UAC (Användarkontokontroll)
- Skriv **UAC** i Start-menyn och välj **Ändra inställningar för användarkontokontroll**.
- Dra reglaget till högsta säkerhetsnivå.

## 4. Installera Antivirusprogram
- Installera ett antivirusprogram som **Windows Defender** eller tredjeparts antiviruslösningar.
- Använd webbläsartillägg för att varna om osäkra nedladdningar.

## 5. Kontrollera Digitala Signaturer och Certifikat
- Högerklicka på installationsfilen > **Egenskaper** > **Digitala signaturer** för att verifiera om programmet är betrott.

## 6. Använd Gruppolicy för att Blockera Oönskade Appar
- Öppna **gpedit.msc** > **Datorkonfiguration** > **Administrativa mallar** > **Windows Installer**.
- Aktivera policyn **Endast installerade program som är godkända**.

## 7. Använd AppLocker (Pro och Enterprise)
- Öppna **gpedit.msc** > **Windows-komponenter** > **AppLocker** och definiera regler för tillåtna appar.



9. Använd en webbläsartillägg som blockerar skadliga skript och annonser

- **Webbläsartillägg**: Installera tillägg som blockerar skript (t.ex. NoScript) och annonser (t.ex. uBlock Origin) för att minska risken att oavsiktligt ladda ner skadlig programvara.

Varför?

Att använda ett webbläsartillägg som blockerar skadliga skript och annonser är ett effektivt sätt att skydda din enhet från säkerhetshot, förbättra din integritet online och skapa en bättre surfupplevelse. Genom att blockera farliga skript och oönskade annonser minskar du risken för infektioner, förbättrar systemets prestanda och gör ditt online-liv säkrare och mer bekvämt. Det är en enkel men kraftfull åtgärd för att öka både säkerheten och bekvämligheten när du surfar på nätet.



10. Kontrollera och hantera installerade program

- **Avinstallera oanvända program**: Ta bort gamla eller oanvända program från systemet, eftersom de kan innehålla sårbarheter.
- **Programuppdateringar**: Håll alla installerade program uppdaterade, eftersom äldre versioner ofta innehåller säkerhetshål.

Varför?

Att kontrollera och hantera installerade program är en viktig del av att hålla din dator säker, effektiv och stabil. Genom att ta bort oönskade program, hålla dina program uppdaterade, och förhindra installation av skadlig eller oönskad programvara kan du minska risken för säkerhetsproblem, förbättra prestanda och skapa en bättre användarupplevelse. Regelbundna kontroller gör att du har full kontroll över vad som körs på din dator och hjälper dig att hålla den i gott skick.



Hur?

Lista installerade program:
Get-WmiObject -Class Win32_Product


Installera ett program (med winget):

winget install <programnamn>



## 11. Övervaka systemet med säkerhetsverktyg

- **Windows Event Viewer**: Använd Event Viewer för att övervaka systemloggar och identifiera misstänkt aktivitet.
- **Säkerhetslösningar från tredje part**: Använd säkerhetsövervakningslösningar som kan upptäcka intrång och anomalier i realtid.

Varför?

Säkerhetsverktyg är viktiga för att skydda din dator mot en mängd olika hot, från skadlig programvara och hackare till identitetsstöld och systeminstabilitet. Genom att använda säkerhetsverktyg kan du skydda din data, förbättra systemets prestanda och se till att både din dator och dina onlineaktiviteter är säkra. Utan rätt säkerhetsverktyg ökar risken för att utsättas för cyberattacker, dataläckor och andra säkerhetsproblem.

Hur?

PowerShell kan användas för att övervaka systemstatus och säkerhetsinställningar via kommandon.

#### Exempel på PowerShell-kommandon:
- **Visa aktuella användarkonton:**
  ```powershell
  Get-LocalUser


## 12. Använd ett VPN

- **VPN (Virtual Private Network)**: Använd ett VPN när du är på offentliga Wi-Fi-nätverk för att skydda din internettrafik och förhindra att tredje parter spårar din aktivitet.

Varför?

En VPN är ett kraftfullt verktyg som skyddar din integritet, säkerhet och frihet på internet. Genom att kryptera din trafik och dölja din IP-adress kan en VPN förhindra spårning, skydda dina data från hackare och andra externa hot, ge dig åtkomst till blockerat innehåll, och ge dig större anonymitet när du surfar. Att använda en VPN är särskilt viktigt när du använder offentliga nätverk, vill undvika censur eller helt enkelt vill skydda din privata information online.

Hur?

Powershell

rasdial "MittVPN" användarnamn lösenord



## Slutsats

Genom att följa dessa säkerhetsprinciper kan du skydda ditt Windows-system från många vanliga säkerhetshot. Det är också viktigt att hålla sig informerad om nya säkerhetshot och uppdatera sina skyddsåtgärder därefter.
