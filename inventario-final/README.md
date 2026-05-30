# 🏥 Inventari BST — Transfusions

## Objectiu

Aquesta eina permet als treballadors del Servei de Transfusions de BST realitzar el control d'inventari de material de manera àgil i digital, substituint el formulari en paper.

El treballador escaneja el codi de barres de cada producte amb el mòbil, introdueix la quantitat a demanar (COMANDA) o les existències actuals, i al final descarrega un Excel amb totes les dades per imprimir o enviar.

---

## Com funciona

### 1. Accés
- Obre la URL de l'aplicació des de qualsevol dispositiu amb navegador
- **URL**: `https://inventari-1.onrender.com`
- Escaneja el QR que apareix a la pantalla per accedir des del mòbil

### 2. Identificació
- Introdueix el teu nom o número d'empleat
- Aquesta informació quedarà registrada a cada comanda

### 3. Escanejar productes
- Prem **"Activar càmera"** i apunta al codi de barres del producte
- O introdueix el codi manualment al camp de text
- L'aplicació mostrarà el nom del producte, la unitat de mesura i l'estoc ideal

### 4. Introducció de quantitats
- **Productes normals**: introdueix la quantitat a demanar (COMANDA)
- **Productes marcats en taronja** ("NOMÉS ANOTAR EXISTÈNCIES"): introdueix les unitats que hi ha ara mateix
- Utilitza els botons **+** i **−** o escriu directament la quantitat
- Prem **"Guardar"** per confirmar

### 5. Seguiment del progrés
- La barra de progrés indica quants productes s'han escanejat del total
- Quan arribi al 100% vol dir que s'han revisat tots els productes del catàleg

### 6. Descarregar l'Excel
- Prem **"Descarregar Excel"** per obtenir el formulari complet
- L'Excel inclou la data, les quantitats introduïdes i el nom del treballador
- Es pot imprimir o enviar directament

---

## Estructura tècnica

| Fitxer | Descripció |
|--------|------------|
| `app.py` | Servidor Flask amb totes les rutes i lògica |
| `templates/index.html` | Interfície web de l'aplicació |
| `Formulario_Inventario_Transfusiones.xlsx` | Catàleg de productes i plantilla de l'informe |
| `requirements.txt` | Dependències Python |
| `Procfile` | Configuració per a Render |

---

## Executar en local (per a desenvolupament)

```bash
pip3 install flask openpyxl gunicorn qrcode pillow
python3 app.py
```

Obre `http://127.0.0.1:8080` al navegador.

---

## Notes importants

- Les dades de la sessió **no es guarden** quan es reinicia el servidor — cada sessió comença de zero
- El catàleg de productes prové del fitxer Excel inclòs al projecte
- Per modificar el catàleg, cal editar l'Excel i tornar a desplegar
- En el pla gratuït de Render, l'aplicació pot trigar uns segons a carregar si ha estat inactiva més de 15 minuts
