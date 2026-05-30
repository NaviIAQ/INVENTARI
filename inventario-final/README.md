# Inventari BST — Transfusions

## Executar en local (Mac)

```bash
cd inventario-final
pip3 install flask openpyxl gunicorn
python3 app.py
```

Obre http://127.0.0.1:8080 al navegador.

## Pujar a Render (accés des de qualsevol lloc)

1. Puja aquesta carpeta a GitHub
2. Connecta el repositori a Render.com
3. Render detecta el Procfile i ho desplega automàticament
4. Obtens una URL https://xxx.onrender.com

## Ús

1. Identifica't amb el teu nom
2. Escaneja el codi de barres del producte
3. Introdueix la quantitat a demanar (COMANDA)
4. Guarda
5. Al final descarrega l'Excel amb totes les comandes i la data/hora
