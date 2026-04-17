# LAN síť – KOVAC

## 📌 Zadání

Vytvoření LAN sítě v Cisco Packet Traceru obsahující:

* 2× switch (S1, S2)
* 2× PC (PC1, PC2)
* 2× server (SRV1 – DHCP + DNS, SRV2 – WEB)
* konfigurace pomocí Laptopu přes terminál

---

## 🧮 Výpočet X

Příjmení: **KOVAC**

ASCII hodnoty:

* K = 75
* O = 79
* V = 86
* A = 65
* C = 67

Součet:
75 + 79 + 86 + 65 + 67 = 372

Výpočet:
372 % 256 = **116**

➡️ Síť: **192.168.116.0 /24**

---

## 🌐 IP adresace

| Zařízení          | IP adresa       |
| ----------------- | --------------- |
| S1                | 192.168.116.1   |
| S2                | 192.168.116.2   |
| SRV1 (DHCP + DNS) | 192.168.116.10  |
| SRV2 (WEB)        | 192.168.116.20  |
| PC1               | 192.168.116.100 |
| PC2               | DHCP            |

Maska: 255.255.255.0
Gateway: 192.168.116.1

---

## 🖧 Topologie sítě

* PC1 a PC2 jsou připojeny ke switchi S1
* S1 je propojen se S2
* SRV1 a SRV2 jsou připojeny ke switchi S2
* Laptop slouží ke konfiguraci switchů přes konzoli

---

## ⚙️ Konfigurace

### 🔹 Switche

* nastaven hostname (S1, S2)
* IP adresa na VLAN 1
* default gateway

---

### 🔹 SRV1 (DHCP + DNS)

#### DHCP:

* přiděluje IP adresy od 192.168.116.100
* gateway: 192.168.116.1
* DNS: 192.168.116.10

#### DNS:

* doména: **kovac.cz**
* záznam:
  kovac.cz → 192.168.116.20

---

### 🔹 SRV2 (WEB)

* běží HTTP server
* stránka obsahuje jméno: **KOVAC**

---

### 🔹 PC

#### PC1:

* statická IP konfigurace

#### PC2:

* IP adresa získána pomocí DHCP

---

## 🧪 Testování

Na PC1 bylo provedeno:

### ✔️ Kontrola IP

* příkaz: ipconfig

### ✔️ Ping na server

* ping 192.168.116.20 → OK

### ✔️ Ping přes DNS

* ping kovac.cz → OK

### ✔️ Web

* otevření http://kovac.cz → OK
  
