# Real Estate Project Description Exchange Format

This document describes a standard format for exchanging real estate project descriptions to interconnect software systems specialized in real estate. The format is structured using JSON and contains information about the project holder (the individual) and the real estate project itself.

## Project Holder (Applicant)

- `salutation` (string) : Salutation of the applicant (Salutation du demandeur).
  - (Possible values: "Mr." (Monsieur), "Mrs." (Madame), "Miss" (Mademoiselle), etc.)
- `firstName` (string) : First name of the applicant (Prénom du demandeur).
- `lastName` (string) : Last name of the applicant (Nom du demandeur).
- `dateOfBirth` (date) : Date of birth of the applicant (Date de naissance du demandeur).
- `maritalStatus` (string) : Marital status of the applicant (Situation maritale du demandeur).
  - (Possible values: "Single" (Célibataire), "Married" (Marié(e)), "Divorced" (Divorcé(e)), "Widow/Widower" (Veuf/Veuve), etc.)
- `numberOfChildren` (integer) : Number of children (Nombre d'enfants) of the applicant.
- `children` (array) : List of children (Liste des enfants) of the applicant.
  - Each child object includes:
    - `firstName` (string) : First name of the child (Prénom de l'enfant).
    - `lastName` (string) : Last name of the child (Nom de l'enfant).
    - `dateOfBirth` (date) : Date of birth of the child (Date de naissance de l'enfant).
    - `situation` (string) : Situation of the child (Situation de l'enfant).

- `address` (Address - Adresse) : Contact address of the applicant (Adresse de contact du demandeur).
  - `id` (string) : Address identifier (Identifiant de l'adresse).
  - `addressLine` (string) : Address line (Ligne d'adresse).
  - `streetNumber` (string) : Street number (Numéro de rue).
  - `street` (string) : Street (Rue).
  - `zipCode` (string) : Zip code (Code postal).
  - `city` (string) : City (Ville).
  - `country` (string) : Country (Pays).
  - `lng` (float) : Longitude (Longitude).
  - `lat` (float) : Latitude (Latitude).
  - `name` (string) : Name of the address (Nom de l'adresse).
  - `zone` (array) : Zone coordinates (Coordonnées de zone).
    - Each zone object includes:
      - `lng` (float) : Longitude (Longitude) of the zone.
      - `lat` (float) : Latitude (Latitude) of the zone.

- `email` (string) : Email address (Adresse électronique) of the applicant.
- `homePhoneNumber` (string) : Home phone number (Numéro de téléphone domicile) of the applicant.
- `mobilePhoneNumber` (string) : Mobile phone number (Numéro de téléphone portable) of the applicant.
- `workPhoneNumber` (string) : Work phone number (Numéro de téléphone professionnel) of the applicant.
- `preferredPhoneNumber` (string) : Preferred phone number (Numéro de téléphone préféré) of the applicant.
- `profession` (Profession - Profession) : Profession information (Informations sur la profession) of the applicant.
  - `label` (string) : Label or title (Libellé) of the profession.
  - `situation` (string) : Occupational situation (Situation professionnelle) of the applicant.
    - (Possible values: "Employee" (Employé), "Self-employed" (Indépendant), "Student" (Étudiant), etc.)
  - `category` (string) : Socio-professional category (Catégorie socio-professionnelle) of the applicant.
    - (Possible values: "Managerial" (Cadre), "Laborer" (Ouvrier), "Farmer" (Agriculteur), etc.)

## Real Estate Project (Project)

- `projectType` (string) : Type of real estate project (Type de projet immobilier).
  - (Possible values: "Purchase" (Achat), "Sale" (Vente), "Rental" (Location), etc.)
- `realtorEmail` (string) : Email address of the realtor (Adresse électronique du courtier immobilier).
- `realtorName` (string) : Name of the realtor (Nom du courtier immobilier).
- `createdAt` (datetime) : Date and time when the project was created (Date et heure de création du projet).
- `uniqueIdentifier` (string) : Unique identifier of the project (Identifiant unique du projet).

### Purchase Data (Buy Data - Données d'Achat)

- `propertyType` (string) : Type of property being sought (Type de propriété recherchée).
  - (Possible values: "Apartment" (Appartement), "House" (Maison), "Land" (Terrain), etc.)
- `propertyLocation` (Property Location - Emplacement du bien) : Location details of the property (Détails de l'emplacement du bien).
  - `addressLine` (string) : Address line (Ligne d'adresse).
  - `streetNumber` (string) : Street number (Numéro de rue).
  - `street` (string) : Street (Rue).
  - `zipCode` (string) : Zip code (Code postal).
  - `city` (string) : City (Ville).
  - `country` (string) : Country (Pays).
  - `lng` (float) : Longitude (Longitude).
  - `lat` (float) : Latitude (Latitude).
  - `name` (string) : Name of the location (Nom de l'emplacement).
  - `radius` (float) : Search radius (Rayon de recherche).

- `propertyDetails` (Property Details - Détails du bien) : Details about the property (Détails sur le bien).
  - `roomNumber` (integer) : Number of rooms (Nombre de pièces).
  - `surface` (float) : Surface area (Surface).
  - `areaSurface` (float) : Area surface (Surface de la zone).
  - `floorLevel` (integer) : Floor level (Niveau de l'étage).
  - `numberOfFloors` (integer) : Number of floors (Nombre d'étages).
  - `bathrooms` (integer) : Number of bathrooms (Nombre de salles de bains).
  - `bedrooms` (integer) : Number of bedrooms (Nombre de chambres).
  - `garageSpaces` (integer) : Number of garage spaces (Nombre de places de garage).
  - `parkingSpaces` (integer) : Number of parking spaces (Nombre de places de parking).
  - `garden` (boolean) : Whether there is a garden (Jardin).
  - `balcony` (boolean) : Whether there is a balcony (Balcon).
  - `condition` (string) : Property condition (État général du bien).
    - (Possible values: "New" (Neuf), "To renovate" (À rénover), "Good condition" (Bon état), etc.)
  - `orientation` (string) : Property orientation (Orientation du bien).
    - (Possible values: "North" (Nord), "South" (Sud), "East" (Est), "West" (Ouest), etc.)

- `financialInformations` (Financial Informations - Informations financières) : Financial details related to the property search (Détails financiers liés à la recherche de propriété).
  - `maxPropertyPrice` (float) : Maximum property price (Prix maximum de la propriété).
  - `maxRenovationCost` (float) : Maximum renovation cost (Coût maximum des travaux de rénovation).
  - `maxProjectPrice` (float) : Maximum project price (Prix maximum du projet).
  - `contributionAmount` (float) : Contribution amount (Montant de la contribution).
  - `financingValidated` (boolean) : Whether financing is validated (Financement validé).

- `proximity` (Proximity - Proximité) : Desired proximity to various facilities and services (Proximité souhaitée aux installations et services).
  - `school` (boolean) : Proximity to schools (Proximité des écoles).
  - `nursery` (boolean) : Proximity to nurseries (Proximité des crèches).
  - `hospital` (boolean) : Proximity to hospitals (Proximité des hôpitaux).
  - `shops` (boolean) : Proximity to shops (Proximité des commerces).

### Sale Data (Sell Data - Données de Vente)

- `propertyType` (string) : Type of property being sold (Type de propriété à vendre).
  - (Possible values: "Apartment" (Appartement), "House" (Maison), "Land" (Terrain), etc.)
- `roomNumber` (integer) : Number of rooms (Nombre de pièces) in the property.
- `surface` (float) : Surface area (Surface) of the property.
- `areaSurface` (float) : Area surface (Surface de la zone) of the property.
- `floorLevel` (integer) : Floor level (Niveau de l'étage) of the property.
- `numberOfFloors` (integer) : Number of floors (Nombre d'étages) in the property.
- `condition` (string) : Property condition (État général du bien).
  - (Possible values: "New" (Neuf), "To renovate" (À rénover), "Good condition" (Bon état), etc.)
- `orientation` (string) : Property orientation (Orientation du bien).
  - (Possible values: "North" (Nord), "South" (Sud), "East" (Est), "West" (Ouest), etc.)

- `propertyLocation` (Property Location - Emplacement du bien) : Location details of the property (Détails de l'emplacement du bien).
  - `id` (string) : Address identifier (Identifiant de l'adresse).
  - `addressLine` (string) : Address line (Ligne d'adresse).
  - `streetNumber` (string) : Street number (Numéro de rue).
  - `street` (string) : Street (Rue).
  - `zipCode` (string) : Zip code (Code postal).
  - `city` (string) : City (Ville).
  - `country` (string) : Country (Pays).
  - `lng` (float) : Longitude (Longitude).
  - `lat` (float) : Latitude (Latitude).
  - `name` (string) : Name of the location (Nom de l'emplacement).
  - `zone` (array) : Zone coordinates (Coordonnées de zone).
    - Each zone object includes:
      - `lng` (float) : Longitude (Longitude) of the zone.
      - `lat` (float) : Latitude (Latitude) of the zone.

- `financialInformations` (Financial Informations - Informations financières) : Financial details related to the property sale (Détails financiers liés à la vente de la propriété).
  - `expectedPrice` (float) : Expected sale price (Prix de vente prévu).
  - `estimatedRenovationCost` (float) : Estimated renovation cost (Coût estimé des travaux de rénovation).
  - `professionalEstimatedPrice` (float) : Professional estimated price (Prix estimé par un professionnel).

- `proximity` (Proximity - Proximité) : Desired proximity to various facilities and services (Proximité souhaitée aux installations et services).
  - `school` (boolean) : Proximity to schools (Proximité des écoles).
  - `nursery` (boolean) : Proximity to nurseries (Proximité des crèches).
  - `hospital` (boolean) : Proximity to hospitals (Proximité des hôpitaux).
  - `shops` (boolean) : Proximity to shops (Proximité des commerces).
