# Service SOAP avec Apache CXF

Service web SOAP utilisant Apache CXF et JAX-WS, conforme aux standards Java EE pour les services web.

## 🎯 Objectif

Créer et tester un service SOAP offrant deux opérations :
1. **SayHello** : Retourne un message de salutation personnalisé
2. **FindPerson** : Retourne un objet Person sérialisé en XML

## 🚀 Démarrage rapide

### Prérequis
- Java 11+
- Maven 3.6+

### Lancer le serveur
```bash
./start-server.sh
```

Le service sera accessible à : **http://localhost:8080/services/hello**

WSDL disponible à : **http://localhost:8080/services/hello?wsdl**

## 📁 Structure du projet

```
src/main/java/com/acme/cxf/
├── Server.java                 # Serveur principal (démarrage)
├── api/
│   └── HelloService.java       # Interface du service (@WebService)
├── impl/
│   └── HelloServiceImpl.java   # Implémentation du service
└── model/
    └── Person.java             # Modèle de données JAXB
```

## 🧪 Tests

### Avec curl

**Test SayHello :**
```bash
curl -X POST -H "Content-Type: text/xml" \
  -d @test-sayHello.xml \
  http://localhost:8080/services/hello
```

**Réponse :**
```xml
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
   <soap:Body>
      <ns2:SayHelloResponse xmlns:ns2="http://api.cxf.acme.com/">
         <greeting>Bonjour, Lachgar</greeting>
      </ns2:SayHelloResponse>
   </soap:Body>
</soap:Envelope>
```

**Test FindPerson :**
```bash
curl -X POST -H "Content-Type: text/xml" \
  -d @test-findPerson.xml \
  http://localhost:8080/services/hello
```

**Réponse :**
```xml
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
   <soap:Body>
      <ns2:FindPersonResponse xmlns:ns2="http://api.cxf.acme.com/">
         <person>
            <age>36</age>
            <id>P-001</id>
            <name>Ada Lovelace</name>
         </person>
      </ns2:FindPersonResponse>
   </soap:Body>
</soap:Envelope>
```

### Avec SoapUI

Voir le guide détaillé : [GUIDE_SOAPUI.md](GUIDE_SOAPUI.md)

## 🛠️ Technologies utilisées

| Technologie | Version | Rôle |
|-------------|---------|------|
| Apache CXF | 3.5.5 | Framework SOAP |
| JAX-WS API | 2.3.1 | API Web Services |
| JAXB | 2.3.5 | Sérialisation XML |
| Jetty | 9.x | Serveur HTTP embarqué |
| Java | 11+ | Plateforme |

## 📝 Fonctionnalités

### Opération SayHello
- **Entrée** : String name
- **Sortie** : String greeting
- **Exemple** : "Lachgar" → "Bonjour, Lachgar"

### Opération FindPerson
- **Entrée** : String id
- **Sortie** : Person object
- **Champs** : id, name, age
- **Exemple** : "P-001" → Person(id="P-001", name="Ada Lovelace", age=36)

## 🔧 Configuration Maven

Le projet utilise :
- `cxf-rt-frontend-jaxws` : Support JAX-WS
- `cxf-rt-transports-http-jetty` : Transport HTTP avec Jetty
- `jaxws-api` et `jaxws-rt` : API et runtime JAX-WS

## 📦 Build

```bash
mvn clean package
```

## 🎓 Points d'apprentissage

1. **Annotations JAX-WS** : `@WebService`, `@WebMethod`, `@WebParam`, `@WebResult`
2. **Annotations JAXB** : `@XmlRootElement`, `@XmlElement`
3. **Apache CXF** : Configuration et déploiement d'un service SOAP
4. **Contrat WSDL** : Génération automatique depuis le code Java
5. **Sérialisation** : Transformation automatique Java ↔ XML

## ✅ Résultat attendu (Étape 7)

- ✅ Service SOAP démarré et accessible
- ✅ WSDL généré et consultable
- ✅ Opération SayHello retourne une salutation
- ✅ Opération FindPerson retourne un objet Person sérialisé
- ✅ Tests réussis avec SoapUI ou curl
- ✅ Conformité contractuelle validée

## 📚 Ressources

- [Apache CXF Documentation](https://cxf.apache.org/)
- [JAX-WS Tutorial](https://docs.oracle.com/javaee/7/tutorial/jaxws.htm)
- [JAXB Tutorial](https://docs.oracle.com/javase/tutorial/jaxb/)

---

**Auteur** : Projet d'apprentissage SOAP avec Apache CXF  
**Date** : 2025
