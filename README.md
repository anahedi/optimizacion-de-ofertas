# Optimización de recomendaciones
Este repo contiene el motor de ofertas inteligentes que Clubers usa para llenar mesas vacías y consentir a los comensales con descuentos. Instálalo, pasa tus datos de órdenes y restaurantes ¡y empieza a ver cómo se disparan tus ventas! 

El código de este repositorio se encarga de:

Perfilado inteligente del usuario (categorías, reseñas y ubicación).
Motor híbrido de recomendación (colaborativo + contenido + proximidad).

🗂️ Estructura del repositorio

⚙️ Instalación rápida

# Clona el repo
git clone https://github.com/tu-org/clubers.git
cd clubers

# Crea un entorno (opcional pero recomendado)
python -m venv .venv
source .venv/bin/activate  # Win: .venv\Scripts\activate

# Instala dependencias
pip install -r requirements.txt

🚀 Ejecución básica

# 1. Procesa tus datos
# 2. Actualiza el modelo
# 3. Crea recomendaciones personalizadas

📊 Principales métricas


🔍 Cómo funciona el modelo

graph TD
    A[Eventos de compra] --> B[Preprocesamiento & Features]
    B --> C[Modelo híbrido]
    C -->|Top‑N ofertas| D[Scheduler]
    D --> E[App & Notificaciones]
    E -->|Clicks & ventas| A

Modelo híbrido: mezcla TF‑IDF de descripciones, embeddings Word2Vec de reseñas y KNN basado en ubicación (Haversine).

📒 Data Requirements
Tabla
Campos clave
ordenes
id_orden, cliente_id, proveedor_id, monto, timestamp
socios_proveedores
proveedor_id, categoria, subcategoria, lat, lon
platillos
plato_id, proveedor_id, descripcion
reseñas
cliente_id, proveedor_id, texto, rating
Carga tus CSV a data/raw/ con esos nombres o ajusta paths en config.py.

🤝 Contribuir
Haz un fork y crea tu rama: git checkout -b feature/mi-mejora
Abre un PR describiendo qué y por qué.

📄 Licencia
MIT – si algo falla, manda issue y lo checamos juntos.

🥳 Créditos
Made with mucho cariño por el squad de Modatta ¡Súmate y cambia la manera en que México disfruta sus comidas! :D

