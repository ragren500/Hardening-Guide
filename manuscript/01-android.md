# Hardening Guide för Android

**OBS** Denna guide är under utveckling och uppdateras löpande!

## Introduktion

Att härda Android innebär att du stärker säkerheten i operativsystemet och skyddar din enhet mot säkerhetshot såsom obehörig åtkomst, dataläckor och skadlig programvara. Guiden nedan innehåller grundläggande och avancerade säkerhetsåtgärder för Android-enheter.

## Android Hardening Guide

Denna sektion innehåller säkerhetsåtgärder för att härda Android och skydda det mot olika hot.

## 1. Uppdatera Android regelbundet

Varför: För att se till att enheten har de senaste säkerhetsuppdateringarna från tillverkaren.

- Gå till **Inställningar → System → Systemuppdatering**.
- Sök efter uppdateringar och installera dem om sådana finns.

## 2. Använd ett säkert skärmlås

Varför: För att förhindra obehörig åtkomst till enheten.

- Gå till **Inställningar → Säkerhet → Skärmlås**.
- Välj PIN-kod, lösenord eller biometrisk inloggning (fingeravtryck eller ansiktsigenkänning).

## 3. Kryptera enheten

Varför: För att skydda lagrad data vid stöld eller förlust.

- De flesta nyare Android-enheter är krypterade som standard.
- Kontrollera detta under **Inställningar → Säkerhet → Kryptering & referenser**.

## 4. Inaktivera USB-felsökning

Varför: För att förhindra obehörig åtkomst via fysisk anslutning.

- Gå till **Inställningar → Utvecklaralternativ**.
- Stäng av **USB-felsökning**.

## 5. Aktivera Google Play Protect

Varför: För att skydda mot skadliga appar installerade från Google Play.

- Öppna **Google Play Butik → Profilbild → Play Protect**.
- Se till att skanning efter säkerhetshot är aktiverad.

## 6. Begränsa installation av appar från okända källor

Varför: För att minska risken att installera skadlig programvara.

- Gå till **Inställningar → Appar → Specialåtkomst → Installera okända appar**.
- Inaktivera för alla appar där det inte är absolut nödvändigt.

## 7. Ta bort oanvända appar

Varför: För att minska attackytan.

- Gå till **Inställningar → Appar** och ta bort appar du inte använder eller litar på.

## 8. Begränsa app-behörigheter

Varför: För att minimera åtkomsten till personlig information.

- Gå till **Inställningar → Sekretess → Behörighetshanterare**.
- Granska och justera behörigheter för varje kategori (plats, kamera, mikrofon osv).

## 9. Aktivera tvåfaktorsautentisering (2FA)

Varför: För att stärka skyddet för ditt Google-konto.

- Besök [https://myaccount.google.com/security](https://myaccount.google.com/security).
- Aktivera tvåstegsverifiering och följ anvisningarna.

## 10. Använd ett VPN vid osäkra nätverk

Varför: För att kryptera nätverkstrafik på publika Wi-Fi.

- Installera en betrodd VPN-app från Google Play.
- Aktivera VPN vid anslutning till okända eller offentliga nätverk.

## 11. Inaktivera Bluetooth när det inte används

Varför: För att minska risken för trådlösa attacker.

- Stäng av Bluetooth från snabbmenyn eller via **Inställningar → Anslutna enheter**.

## 12. Inaktivera platstjänster när det inte behövs

Varför: För att skydda din platsinformation från obehörig åtkomst.

- Gå till **Inställningar → Plats**.
- Inaktivera globalt eller justera åtkomst för specifika appar.

## 13. Använd ett säkert låsskärmsmeddelande

Varför: För att undvika exponering av känslig information.

- Gå till **Inställningar → Skärm → Låsskärmsinställningar**.
- Undvik att visa kontaktuppgifter eller annat privat innehåll.

## 14. Aktivera Hitta min enhet

Varför: För att kunna spåra och radera enheten vid stöld eller förlust.

- Gå till **Inställningar → Säkerhet → Hitta min enhet** och aktivera.

## 15. Begränsa annonseringsidentifierare

Varför: För att minska spårning av användarbeteende.

- Gå till **Inställningar → Google → Annonser** och välj att avaktivera personanpassade annonser.

## 16. Använd en säker webbläsare

Varför: För att minska risken vid surfning.

- Använd webbläsare som **Firefox**, **DuckDuckGo** eller **Brave** med inbyggt spårskydd.

## 17. Begränsa aviseringar på låsskärmen

Varför: För att förhindra att känslig information visas när skärmen är låst.

- Gå till **Inställningar → Aviseringar → Låsskärm** och välj att dölja känsligt innehåll.

## 18. Använd en lösenordshanterare

Varför: För att generera och spara starka lösenord.

- Installera och använd appar som **Bitwarden**, **1Password** eller **KeePassDX**.

## 19. Undvik att roota enheten

Varför: För att bibehålla systemets säkerhetsbegränsningar.

- Roota endast om du har mycket god kunskap och starkt behov – det rekommenderas inte för vanliga användare.

## 20. Starta om enheten regelbundet

Varför: För att stoppa vissa bakgrundsprocesser och temporära angrepp.

- Starta om enheten manuellt minst en gång i veckan.

