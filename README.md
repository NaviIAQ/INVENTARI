# 🏥 Inventari 

> Eina digital de control d'inventari. Substitueix el formulari en paper per un sistema àgil, accessible des de qualsevol dispositiu mòbil.

**URL de l'aplicació:** https://inventari-1.onrender.com

---

## 🎯 Objectiu

Aquesta eina permet als treballadors realitzar el control d'inventari de material de manera àgil i digital. El treballador escaneja el codi de barres de cada producte amb el mòbil, introdueix la quantitat i descarrega un Excel complet al final de la sessió, llest per imprimir o enviar.

---

## 📱 Com funciona

### Flux d'ús pas a pas

```
Escaneja el QR → Identifica't → Escaneja productes → Introdueix quantitats → Descarrega Excel
```

<img width="726" height="776" alt="Flux d&#39;us" src="https://github.com/user-attachments/assets/a5fe1c9f-4500-4178-84fa-a66e102b9a6d" />


**1. Accés**
Escaneja el codi QR que apareix a l'aplicació o accedeix directament a la URL. No cal instal·lar res.

**2. Identificació**
Introdueix el teu nom o número d'empleat. Quedarà registrat a cada comanda.

**3. Escaneig del producte**
Prem "Activar càmera" i apunta al codi de barres. El sistema reconeix el producte i mostra:
- Nom complet del producte
- Unitat de mesura
- Estoc ideal

**4. Introducció de la quantitat**
- **Productes normals** → introdueix la quantitat a demanar (COMANDA)
- **Productes marcats en taronja** → introdueix les existències actuals (Només anotar existències)

Utilitza els botons **+** i **−** per comptar de un en un, o escriu directament la xifra.

**5. Seguiment del progrés**
La barra de progrés indica quants productes s'han revisat del total del catàleg. Prem "Veure productes pendents" per veure la llista dels que falten.

**6. Exportació**
Prem **"Descarregar Excel"** per obtenir el formulari original amb la columna COMANDA emplenada, la data i l'hora de cada registre.

---

## ✨ Característiques

| Característica | Descripció |
|---|---|
| 📷 Escàner de codi de barres | Compatible amb EAN-13, EAN-8, Code128, Code39 i UPC |
| 📊 Barra de progrés | Indica en temps real quants productes s'han revisat |
| 📋 Llista de pendents | Mostra els productes que encara no s'han escanejat |
| ⚠️ Seccions diferenciades | Els productes de "Només anotar existències" apareixen marcats en taronja |
| 📄 Exportació a Excel | Genera el formulari original amb les dades emplenades |
| 🌐 Disponible 24/7 | Allotjada al núvol, sense necessitat de cap ordinador encès |
| 🔒 HTTPS | Connexió segura, compatible amb tots els navegadors mòbils |
| 👤 Multiusuari | Diversos treballadors poden accedir simultàniament |

---

## 🚀 Millores futures previstes

### 🔒 Pla de servidor privat (7 €/mes — Render Starter)
Actualment l'aplicació utilitza el pla gratuït de Render, que té algunes limitacions:
- El servidor s'adorm si no hi ha activitat durant 15 minuts
- El repositori de codi ha de ser públic

Amb el pla de pagament (7 €/mes) s'obtindria:
- Servidor sempre actiu, sense temps d'espera
- Repositori privat, codi protegit
- Major velocitat de resposta

### 🤖 Agent automàtic de comandes
Una millora molt interessant seria integrar un agent d'intel·ligència artificial que, un cop generat el PDF/Excel de l'inventari, analitzés automàticament els productes per sota del mínim i generés la comanda corresponent al proveïdor, ja sigui per correu electrònic o mitjançant integració amb el sistema de gestió de l'hospital.

### 📊 Historial d'inventaris
Guardar un registre de totes les sessions anteriors per poder consultar l'evolució del stock al llarg del temps i detectar tendències de consum.

### 🔔 Alertes automàtiques
Enviar una notificació automàtica per correu quan es detectin productes per sota del mínim, sense necessitat de generar l'informe manualment.

### 👥 Gestió d'usuaris
Afegir un sistema d'autenticació per controlar qui accedeix a l'aplicació i portar un registre d'activitat per treballador.

---

## 🛠️ Tecnologia

- **Backend:** Python + Flask
- **Processament Excel:** OpenPyXL
- **QR:** QRCode + Pillow
- **Desplegament:** Render (núvol gratuït)
- **Repositori:** GitHub

---

## 🗂️ Estructura del projecte

```
inventario-final/
├── app.py                                    # Servidor Flask + API REST
├── templates/
│   └── index.html                            # Interfície web
├── Formulario_Inventario_Transfusiones.xlsx  # Catàleg i plantilla
├── requirements.txt                          # Dependències Python
├── Procfile                                  # Configuració Render
└── README.md
```

---

## ⚠️ Notes importants

- Les dades de la sessió **no es guarden** quan es reinicia el servidor — cada sessió comença de zero
- El catàleg de productes prové del fitxer Excel inclòs al projecte
- En el pla gratuït de Render, l'aplicació pot trigar uns segons a carregar si ha estat inactiva més de 15 minuts
- La càmera del mòbil requereix connexió HTTPS (funcionament correcte a Render)
