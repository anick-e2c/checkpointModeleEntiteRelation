# checkpointModeleEntiteRelation

#### 🏋️ Modèle Entité-Relation (MER) – Exemple concret

 🔹 Entités principales

| Entité	                       |    Attributs
---------------------------------------------------------------------------------------------------------------------
|  Gymnase	                       |    id_gymnase (PK), nom, adresse, telephone
---------------------------------------------------------------------------------------------------------------------
|  Membre	                       |    id_membre (PK), nom, prenom, adresse, date_naissance, sexe, id_gymnase (FK)
---------------------------------------------------------------------------------------------------------------------
|  Coach	                       |    id_coach (PK), nom, prenom, age, specialite
---------------------------------------------------------------------------------------------------------------------
|  Séance	                       |    id_seance (PK), type_sport, horaire, id_gymnase (FK)
---------------------------------------------------------------------------------------------------------------------


#### 🔹 Relations (associatives)
| Relation	                                            | Description
---------------------------------------------------------------------------------------------------------------------

| Inscription (id_membre, id_seance)	
                                                        | ➤ Un membre peut s'inscrire à plusieurs séances.	
                                                        | ➤ Une séance peut accueillir jusqu'à 20 membres.	
                                                        | ➤ Clé primaire composite : (id_membre, id_seance)	
---------------------------------------------------------------------------------------------------------------------

| Animation (id_coach, id_seance) |
---------------------------------------------------------------------------------------------------------------------
                                                        | ➤ Une séance peut être animée par 1 ou 2 coachs.
                                                        | ➤ Un coach peut animer plusieurs séances.
                                                        | ➤ Clé primaire composite : (id_coach, id_seance)
---------------------------------------------------------------------------------------------------------------------


#### 📘 Exemple textuel du modèle

Gymnase (id_gymnase, nom, adresse, téléphone)
    ↑              ↑
    |              |
Membre           Séance (id_seance, type_sport, horaire, id_gymnase)
(id_membre, nom, prénom, adresse, date_naissance, sexe, id_gymnase)
    |              ↑
    |              |
Inscription      Animation
(id_membre,      (id_coach,
 id_seance)       id_seance)
    ↑
Coach (id_coach, nom, prénom, âge, spécialité)
