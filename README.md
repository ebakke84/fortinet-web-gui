# FortiOS Config Generator

En enkel nettside som lager CLI-konfigurasjon for FortiGate med FortiOS 7.6. Alt kjører lokalt i nettleseren. Ingen data sendes noe sted, og det trengs ingen server eller byggesteg.

## Faner

- **IPsec site-to-site**: route-based tunnel med IKEv1/IKEv2, flere subnett og blackhole-ruter. Valgfritt SD-WAN, BGP og NAT for overlappende nett.
- **Interface / VLAN / DHCP**: VLAN-grensesnitt med DHCP-server og internett-policy. Har eget valg for FortiAP/FortiSwitch-nett med CAPWAP, auto-godkjenning, NTP og DHCP option 138.
- **FortiAP**: zero-touch-oppsett der AP-grensesnittet legges til under *NTP: Listen on interfaces*. NTP kreves for FortiLink-enheter, både AP-er og switcher. Fanen har også med egne profiler for FAP-231F, 431F, 221K og 231K. Dekker SSID-er (WPA2/WPA3/OWE/Enterprise), DARRP, band steering, 802.11r/k/v og kanallister som følger valgt kanalbredde.

Hver fane gir tre visninger: utrullingsskript, angre-skript og oppsummering. Du kan også velge VDOM, ta backup (revisjon) før endring og slå på auto-revert.

## Bruk

### Last ned med git clone

```bash
git clone https://github.com/ebakke84/fortinet-web-gui.git
cd fortinet-web-gui
```

Har du satt opp SSH-nøkkel mot GitHub, kan du bruke SSH i stedet:

```bash
git clone git@github.com:ebakke84/fortinet-web-gui.git
```

Hent siste versjon senere med:

```bash
git pull
```

### Åpne siden

Åpne `index.html` direkte i nettleseren:

```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows (PowerShell)
start index.html
```

Du kan også kjøre en enkel lokal webserver og gå til <http://localhost:8000>:

```bash
python3 -m http.server 8000
```

### Publiser på nett

Slå på GitHub Pages under **Settings → Pages → Deploy from a branch → `main` / root**. Siden blir da tilgjengelig på <https://ebakke84.github.io/fortinet-web-gui/>.

## Forbehold

Kontroller alltid generert config i et testmiljø før produksjon. Enkelte kommandoer bør sjekkes mot FortiOS-versjonen din, særlig `set type 221K`, som krever en nyere 7.6-patch.
