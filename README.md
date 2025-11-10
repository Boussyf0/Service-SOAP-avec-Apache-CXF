# Service SOAP avec Apache CXF

Service web SOAP sécurisé avec Apache CXF et JAX-WS.

## 🚀 Démarrage rapide

### Lancer le serveur
```bash
./start-server.sh
```

Le service sera accessible à : **http://localhost:8080/services/hello**

WSDL : **http://localhost:8080/services/hello?wsdl**

### Tester avec le client Java
```bash
./run-client.sh
```

## 🔐 Sécurité

- **Username** : `student`
- **Password** : `secret123`

## 📸 Tests avec SoapUI

### Projet créé
![SoapUI Projet](Screen/Screenshot%202025-11-09%20at%2023.57.56.png)

### Opérations disponibles
![SoapUI Opérations](Screen/Screenshot%202025-11-09%20at%2023.58.59.png)

### Requête SOAP
![Test Requête](Screen/Screenshot%202025-11-10%20at%2000.26.24.png)

### Réponse du service
![Test Réponse](Screen/Screenshot%202025-11-10%20at%2000.28.21.png)

### Configuration WS-Security
![Configuration Auth](Screen/Screenshot%202025-11-10%20at%2000.43.46.png)

### Résultat avec authentification
![Résultat Final](Screen/Screenshot%202025-11-10%20at%2000.46.46.png)

## 📝 Opérations

### SayHello
- **Entrée** : String name
- **Sortie** : String greeting

### FindPerson
- **Entrée** : String id
- **Sortie** : Person (id, name, age)

## 🛠️ Technologies

- Apache CXF 3.5.5
- JAX-WS API 2.3.1
- WS-Security UsernameToken
- Java 11+

## 📚 Documentation

- [GUIDE_SOAPUI.md](GUIDE_SOAPUI.md) - Guide détaillé SoapUI
- [CHECKLIST_VALIDATION_FINALE.txt](CHECKLIST_VALIDATION_FINALE.txt) - Validation complète
- [SCENARIO_SOAPUI_SCREENSHOTS.txt](SCENARIO_SOAPUI_SCREENSHOTS.txt) - Scénario de test

---

**Auteur** : Projet SOAP avec Apache CXF  
**Date** : 2025
