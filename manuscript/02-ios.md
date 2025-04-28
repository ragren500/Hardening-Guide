# Hardening Guide för IOS

**OBS** Denna guide är under utveckling och uppdateras löpande!

## Introduktion

Att härda IOS innebär att du stärker säkerheten i operativsystemet och skyddar din enhet mot säkerhetshot såsom obehörig åtkomst, dataläckor och skadlig programvara. Guiden nedan innehåller grundläggande och avancerade säkerhetsåtgärder för IOS-enheter.

## IOS Hardening Guide

Denna sektion innehåller säkerhetsåtgärder för att härda IOS och skydda det mot olika hot.

## 1. Installera en ren kopia av IOS

Varför: För att säkerställa en säker utgångspunkt utan risk från eventuellt tidigare komprometterade inställningar eller applikationer.

- Säkerhetskopiera viktiga data först.
- Återställ enheten till fabriksinställningar och installera IOS från officiella källor (Apple).
- Undvik att återställa säkerhetskopior från okända eller opålitliga källor.

## 2. Uppdatera IOS regelbundet

Varför: För att skydda mot säkerhetsbrister som upptäcks kontinuerligt.

- Aktivera automatiska uppdateringar:
  - `Inställningar → Allmänt → Programuppdatering → Automatiska uppdateringar → Aktivera "Ladda ner och installera IOS-uppdateringar".`

## 3. Använd stark autentisering

Varför: Förhindrar obehörig åtkomst till din enhet.

- Aktivera Face ID eller Touch ID:
  - `Inställningar → Face ID & lösenkod / Touch ID & lösenkod → Aktivera.`
- Använd ett komplext lösenord:
  - `Inställningar → Face ID & lösenkod → Ange en alfanumerisk lösenkod på minst 8 tecken.`

## 4. Begränsa användning av appbehörigheter

Varför: Minskar risken att appar missbrukar data eller funktioner.

- Granska och begränsa appars åtkomst:
  - `Inställningar → Integritet och säkerhet → Välj relevant kategori (ex. Plats, Kamera, Mikrofon) och granska behörigheter.`

## 5. Aktivera Hitta min iPhone

Varför: För att skydda enheten mot förlust och stöld.

- `Inställningar → Apple-ID → Hitta → Aktivera "Hitta min iPhone".`
- Aktivera `"Skicka senaste plats"` för att spåra enheten även vid lågt batteri.

## 6. Begränsa nätverksanslutningar

Varför: Minskar risken för nätverksrelaterade attacker.

- Anslut endast till betrodda Wi-Fi-nätverk.
- Använd VPN vid anslutning till offentliga Wi-Fi.
- Stäng av automatisk anslutning till öppna nätverk:
  - `Inställningar → Wi-Fi → Fråga vid anslutning.`

## 7. Stäng av onödiga tjänster och funktioner

Varför: Minskar attackytan.

- Inaktivera AirDrop när det inte används:
  - `Inställningar → Allmänt → AirDrop → Endast mottagning av.`
- Inaktivera Bluetooth om det inte används aktivt.

## 8. Använd säker webbläsning och mailhantering

Varför: Skyddar mot nätfiske och skadliga webbsidor.

- Använd Safari med integrerad varning för bedrägliga webbplatser:
  - `Inställningar → Safari → Aktivera "Bedrägerivarning".`
- Var försiktig med länkar och bilagor från okända avsändare i e-post.

## 9. Säkerhetskopiera data regelbundet

Varför: Säkerställer tillgång till data vid en incident.

- Använd säkerhetskopiering via iCloud:
  - `Inställningar → Apple-ID → iCloud → Säkerhetskopia → Aktivera "Säkerhetskopiera till iCloud".`


