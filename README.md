# ⚙️ ArsMedicaTech — Backend

Serveur backend du projet **ArsMedicaTech**, développé en **Flask (Python)**.  
Il gère la logique applicative, les connexions à **SurrealDB** et **Redis**, ainsi que la communication avec le frontend React.

---

## 🧩 Technologies utilisées

| Outil | Description |
|-------|--------------|
| 🐍 **Flask** | API REST principale |
| 🗄️ **SurrealDB** | Base de données orientée graph |
| 🔁 **Redis** | Système de cache et de file de messages |
| 🧠 **Sentry** | Suivi et capture des erreurs |
| 🐳 **Docker** | Conteneurisation des services |
| 🔐 **.env** | Gestion des variables d’environnement |

---

## 🚀 Installation et lancement

### **1️⃣ Cloner le projet**

```bash
git clone https://github.com/j4niro/arsmedicatech-backend.git
cd arsmedicatech-backend
```

---

### **2️⃣ Lancer SurrealDB avec Docker**

```bash
docker run --name arsmedicatech-backend --rm --pull always  -p 8700:8000 -v ./mydata:/mydata -w /mydata  surrealdb/surrealdb:latest-dev start  --user root --pass root
```

---

### **3️⃣ Lancer Redis avec Docker**

```bash
docker run -d --name redis -p 6379:6379 redis
```

---

### **4️⃣ Configurer l’environnement**

Créer un fichier `.env` à la racine du projet avec le contenu suivant :

```ini
# --- SurrealDB ---
SURREALDB_URL=ws://localhost:8700
SURREALDB_NAMESPACE=test
SURREALDB_DATABASE=app
SURREALDB_USER=root
SURREALDB_PASS=root

# --- Sécurité ---
ENCRYPTION_KEY=supersecretkey1234567890
SENTRY_DSN=disabled

# --- Redis ---
REDIS_HOST=localhost
REDIS_PORT=6379

# --- MCP ---
MCP_URL=http://localhost:9000/mcp/
```

---

### **5️⃣ Installer les dépendances Python**

Créez un environnement virtuel et installez les packages requis :

```bash
python -m venv venv
venv\Scripts\activate     # sous Windows
source venv/bin/activate   # sous Linux/Mac

pip install -r requirements.txt
```

---

### **6️⃣ Lancer le serveur Flask**

```bash
python app.py --host=0.0.0.0 --port=3123
```

L’API sera disponible à :  
👉 [http://localhost:3123](http://localhost:3123)

---



