# FortiOS Config Generator

En enkel nettside som lager CLI-konfigurasjon for FortiGate med FortiOS 7.6. Alt kjører lokalt i nettleseren. Ingen data sendes noe sted, og det trengs ingen server eller byggesteg.

## Faner

- **IPsec site-to-site**: route-based tunnel med IKEv1/IKEv2, flere subnett og blackhole-ruter. Valgfritt SD-WAN, BGP og NAT for overlappende nett.
- **Interface / VLAN / DHCP**: VLAN-grensesnitt med DHCP-server og internett-policy. Har eget valg for FortiAP-nett med CAPWAP, auto-godkjenning og DHCP option 138.
- **FortiAP**: zero-touch-oppsett med egne profiler for FAP-231F, 431F, 221K og 231K. Dekker SSID-er (WPA2/WPA3/OWE/Enterprise), DARRP, band steering, 802.11r/k/v og kanallister som følger valgt kanalbredde.

Hver fane gir tre visninger: utrullingsskript, angre-skript og oppsummering. Du kan også velge VDOM, ta backup (revisjon) før endring og slå på auto-revert.

## Bruk

Åpne `index.html` i en nettleser, eller publiser repoet med GitHub Pages: **Settings → Pages → Deploy from a branch → `main` / root**.

## Forbehold

Kontroller alltid generert config i et testmiljø før produksjon. Enkelte kommandoer bør sjekkes mot FortiOS-versjonen din, særlig `set type 221K`, som krever en nyere 7.6-patch.
