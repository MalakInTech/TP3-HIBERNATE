# Gestion des Réservations – JPA / Hibernate / H2

Ce projet est une application Java développée avec **Maven**, utilisant **JPA (Hibernate)** pour la gestion de la persistance des données et **H2** comme base de données en mémoire.

Il permet de gérer un système simple de réservation comprenant :

- 👤 Utilisateurs
- 🏢 Salles
- 🖥️ Équipements
- 📅 Réservations

## 📌 Objectif du TP

À travers ce projet, j’ai appris à :

- Créer et annoter des entités avec `@Entity`, `@Id`, `@GeneratedValue`
- Mettre en place des relations entre entités (`@OneToMany`, `@ManyToOne`, `@ManyToMany`)
- Comprendre le fonctionnement des opérations en cascade
- Utiliser `orphanRemoval`
- Configurer correctement le fichier `persistence.xml`
- Manipuler une base de données **H2 en mémoire**
- Structurer un projet Maven proprement

---

## 🛠️ Technologies utilisées

- Java 8
- Maven
- JPA 2.2
- Hibernate 5
- H2 Database
- Hibernate Validator

---

## ⚙️ Étapes principales de réalisation

### 1️⃣ Création du projet Maven

Création d’un projet Maven afin de gérer automatiquement les dépendances nécessaires (Hibernate, H2, Validator, etc.) et structurer correctement l’application.

---

### 2️⃣ Configuration de la persistance

Création du fichier `persistence.xml` dans le dossier `META-INF` pour :

- Configurer la base de données H2
- Activer la génération automatique des tables
- Définir les propriétés Hibernate

---

### 3️⃣ Création des entités

Création des classes principales :

- `Utilisateur`
- `Salle`
- `Equipement`
- `Reservation`

Chaque classe est annotée avec `@Entity` et contient :

- Une clé primaire (`@Id`)
- Les attributs nécessaires
- Les relations entre entités (`@OneToMany`, `@ManyToOne`, `@ManyToMany`)

---

### 4️⃣ Mise en place des relations

Configuration des relations entre les différentes entités :

- Relation entre Utilisateur et Réservation
- Relation entre Salle et Réservation
- Relation entre Salle et Equipement

Cette étape m'a permis de comprendre le rôle de `mappedBy`, des opérations en cascade et de `orphanRemoval`.

---

### 5️⃣ Test des relations et operations en cascade

Création d'une classe principale `App` pour tester le comportement des entités et de leurs relations.  
Elle permet de vérifier que :

- Les relations `OneToMany`, `ManyToOne` et `ManyToMany` fonctionnent correctement
- Les opérations en **cascade** (persist, merge, remove) se propagent comme prévu
- La **suppression orpheline** (`orphanRemoval`) supprime automatiquement les entités enfants lorsqu’elles sont retirées de la collection de l’entité parente

Les résultats sont affichés dans la console avec les logs SQL générés automatiquement.

---

## 📸 Screenshots de la console

### **1️⃣ Création des tables**

<img width="718" height="418" alt="Creation Tables" src="https://github.com/user-attachments/assets/5faa6bd0-abf3-41a0-b077-43732f7d2cee" />
<img width="653" height="223" alt="Capture d&#39;écran 2026-02-23 131148" src="https://github.com/user-attachments/assets/d2dd97b4-fde9-4a26-b2a0-59e344a58430" />
<img width="826" height="742" alt="Capture d&#39;écran 2026-02-23 131157" src="https://github.com/user-attachments/assets/e9154845-d225-4eda-ab32-e8008248ae9a" />
<img width="790" height="696" alt="Capture d&#39;écran 2026-02-23 131211" src="https://github.com/user-attachments/assets/361b3aa9-6cb3-4860-91c6-450cc0bd4873" />
<img width="645" height="338" alt="Capture d&#39;écran 2026-02-23 131221" src="https://github.com/user-attachments/assets/72d15bd7-fd36-4a74-96d4-dea5580b9bc6" />

## **2️⃣ Test des relations et opérations en cascade**
<img width="694" height="257" alt="Test Relations" src="https://github.com/user-attachments/assets/5d457865-a434-436a-af37-e81580315ccd" />

## **3️⃣ Test de la suppression orpheline**
<img width="786" height="619" alt="Capture d&#39;écran 2026-02-23 131251" src="https://github.com/user-attachments/assets/facaba98-d67b-428f-a873-3154e68047eb" />
<img width="846" height="447" alt="Capture d&#39;écran 2026-02-23 131327" src="https://github.com/user-attachments/assets/e6a9c240-8442-4a3e-bd37-a85d4864b2dc" />
<img width="760" height="456" alt="Capture d&#39;écran 2026-02-23 131354" src="https://github.com/user-attachments/assets/e3e9c188-0978-41de-946f-9296b405068e" />
<img width="822" height="775" alt="Capture d&#39;écran 2026-02-23 131414" src="https://github.com/user-attachments/assets/bf172685-bcd8-4112-8541-1b8a28355fbb" />

## **4️⃣ Test de la relation ManyToMany**
<img width="823" height="611" alt="Capture d&#39;écran 2026-02-23 131429" src="https://github.com/user-attachments/assets/79d156a1-3774-44af-b1fc-5b45842230e5" />
<img width="897" height="773" alt="Capture d&#39;écran 2026-02-23 131439" src="https://github.com/user-attachments/assets/a850ac1a-c84a-4693-96ac-a233f23fc5cf" />
<img width="882" height="611" alt="Capture d&#39;écran 2026-02-23 131456" src="https://github.com/user-attachments/assets/62a85c2d-9bce-44d4-8641-ed17bd724941" />
<img width="798" height="726" alt="Capture d&#39;écran 2026-02-23 131511" src="https://github.com/user-attachments/assets/474f6505-0b1c-48c7-b535-4c4ca1b2a919" />
<img width="746" height="764" alt="Capture d&#39;écran 2026-02-23 131525" src="https://github.com/user-attachments/assets/8717bf0e-969c-4f3e-845c-42f49b88d128" />
<img width="872" height="736" alt="Capture d&#39;écran 2026-02-23 131535" src="https://github.com/user-attachments/assets/6cfacd78-6b52-41d0-8991-9d50351bd1c4" />
<img width="767" height="769" alt="Capture d&#39;écran 2026-02-23 131548" src="https://github.com/user-attachments/assets/34c54c37-be8c-4459-bcb6-3d6813d74e0c" />
<img width="741" height="718" alt="Capture d&#39;écran 2026-02-23 131600" src="https://github.com/user-attachments/assets/8d177dcd-2c21-400e-8685-9b3253210db0" />

---

## 📊 Diagramme de classes et analyse des relations

Le projet comporte quatre entités principales : `Utilisateur`, `Reservation`, `Salle` et `Equipement`.  
Voici un résumé des relations et des annotations utilisées :

### **1️⃣ Relations entre entités**

- **Utilisateur ↔ Reservation**  
  - Type : OneToMany / ManyToOne  
  - Explication : Un utilisateur peut avoir plusieurs réservations, chaque réservation appartient à un seul utilisateur.  
  - Annotation côté parent (`Utilisateur.java`) :
    ```java
    @OneToMany(mappedBy = "utilisateur", cascade = CascadeType.ALL, orphanRemoval = true)
    private List<Reservation> reservations = new ArrayList<>();
    ```
  - Annotation côté enfant (`Reservation.java`) :
    ```java
    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "utilisateur_id", nullable = false)
    private Utilisateur utilisateur;
    ```
  - Particularité : `mappedBy` indique que le **propriétaire de la relation est la réservation** (la table `reservation` contient la clé étrangère `utilisateur_id`).  

- **Salle ↔ Reservation**  
  - Type : OneToMany / ManyToOne  
  - Même logique qu’Utilisateur ↔ Reservation, chaque réservation est liée à une salle.

- **Salle ↔ Equipement**  
  - Type : ManyToMany  
  - Explication : Une salle peut avoir plusieurs équipements et un équipement peut être dans plusieurs salles.  
  - Annotation côté Salle :
    ```java
    @ManyToMany(cascade = {CascadeType.PERSIST, CascadeType.MERGE})
    @JoinTable(
        name = "salle_equipement",
        joinColumns = @JoinColumn(name = "salle_id"),
        inverseJoinColumns = @JoinColumn(name = "equipement_id")
    )
    private Set<Equipement> equipements = new HashSet<>();
    ```
  - Annotation côté Equipement :
    ```java
    @ManyToMany(mappedBy = "equipements")
    private Set<Salle> salles = new HashSet<>();
    ```
    

### **2️⃣ Opérations en cascade**

- **CascadeType.ALL** : propage toutes les opérations (PERSIST, MERGE, REMOVE, REFRESH, DETACH) de l’entité parent vers ses enfants.  
- **CascadeType.PERSIST, CascadeType.MERGE** : seulement persistance et mise a jour.  
- Exemple :  
 ```java
  @OneToMany(mappedBy = "utilisateur", cascade = CascadeType.ALL, orphanRemoval = true)
 ```

### **3️⃣ Suppression orpheline (orphanRemoval)**
- Permet de supprimer automatiquement une entité enfant si elle est retirée de la collection du parent.
```java
@OneToMany(mappedBy = "utilisateur", cascade = CascadeType.ALL, orphanRemoval = true)
private List<Reservation> reservations;
```

### **4️⃣ Méthodes utilitaires pour maintenir la cohérence**
```java
public void addReservation(Reservation reservation) {
    reservations.add(reservation);
    reservation.setUtilisateur(this);
}

public void removeReservation(Reservation reservation) {
    reservations.remove(reservation);
    reservation.setUtilisateur(null);
}
```
- Ces méthodes garantissent que les deux côtés de la relation bidirectionnelle restent synchronisés.


### **5️⃣ Diagramme de classes**
<img width="782" height="585" alt="Capture d&#39;écran 2026-02-23 223952" src="https://github.com/user-attachments/assets/d3910873-cba1-4a51-90f5-f641f8e9e131" />

---

## Auteur
- Nom : Malak El Mallouky
- Filliere : SIR






