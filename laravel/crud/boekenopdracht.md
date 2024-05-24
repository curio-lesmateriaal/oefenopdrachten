# Casus: Boekensysteem

Je bent een ontwikkelaar en je hebt de opdracht gekregen om een eenvoudig boekensysteem te maken met Laravel. In dit systeem moet je boeken en auteurs kunnen beheren. Elk boek moet een auteur hebben en een auteur kan meerdere boeken hebben. Dit betekent dat er een één-op-veel-relatie is tussen auteurs en boeken. De applicatie moet basis CRUD-functionaliteit bevatten voor zowel auteurs als boeken.

## Eisen:
1. **Maken van een migration**
2. **Maken van een seeder**
3. **De juiste routes maken**
4. **Controller maken**
5. **Models maken voor de benodigde items**

## Specificaties:
- Overzicht/Detail opdracht: Er moet een overzicht van alle boeken zijn, en je moet details van een individueel boek kunnen bekijken.
- Er moet een functionaliteit zijn om een nieuw boek aan te maken.
- De database moet minimaal twee tabellen hebben (auteurs en boeken) met een relatie tussen deze tabellen.
- De applicatie is responsive gemaakt (met media queries, bootstrap of tailwind).

## Stappenplan:

### Stap 1: Migraties maken
Maak migraties voor de auteurs en boeken tabellen.

#### Commandos om de migraties aan te maken:
```bash
php artisan make:migration create_authors_table --create=authors
php artisan make:migration create_books_table --create=books
```

#### Definieer de structuur van de `authors` tabel:
- Velden: id, name, timestamps

#### Definieer de structuur van de `books` tabel:
- Velden: id, title, author_id (foreign key), timestamps

### Stap 2: Seeder maken
Maak seeders om testdata in de database te plaatsen.

#### Commandos om de seeders aan te maken:
```bash
php artisan make:seeder AuthorSeeder
php artisan make:seeder BookSeeder
```

#### Voeg testdata toe voor de `authors` tabel:
- Gebruik een factory om meerdere auteurs te genereren.

#### Voeg testdata toe voor de `books` tabel:
- Gebruik een factory om meerdere boeken te genereren en koppel deze aan auteurs.

### Stap 3: Routes maken
Definieer de benodigde routes in `web.php`.

#### Routes voor auteurs:
- index (lijst van auteurs)
- show (details van een auteur)
- create (formulier om een nieuwe auteur aan te maken)
- store (opslaan van een nieuwe auteur)
- edit (formulier om een auteur te bewerken)
- update (opslaan van de bewerkte auteur)
- destroy (verwijderen van een auteur)

#### Routes voor boeken:
- index (lijst van boeken)
- show (details van een boek)
- create (formulier om een nieuw boek aan te maken)
- store (opslaan van een nieuw boek)
- edit (formulier om een boek te bewerken)
- update (opslaan van het bewerkte boek)
- destroy (verwijderen van een boek)

### Stap 4: Controllers maken
Maak controllers voor auteurs en boeken.

#### Commandos om de controllers aan te maken:
```bash
php artisan make:controller AuthorController --resource
php artisan make:controller BookController --resource
```

#### Implementeer de CRUD-functionaliteit in `AuthorController`:
- index: retourneer een overzicht van alle auteurs.
- show: retourneer details van een specifieke auteur.
- create: retourneer een formulier voor het aanmaken van een nieuwe auteur.
- store: sla een nieuwe auteur op in de database.
- edit: retourneer een formulier voor het bewerken van een auteur.
- update: werk de auteur bij in de database.
- destroy: verwijder de auteur uit de database.

#### Implementeer de CRUD-functionaliteit in `BookController`:
- index: retourneer een overzicht van alle boeken.
- show: retourneer details van een specifiek boek.
- create: retourneer een formulier voor het aanmaken van een nieuw boek.
- store: sla een nieuw boek op in de database.
- edit: retourneer een formulier voor het bewerken van een boek.
- update: werk het boek bij in de database.
- destroy: verwijder het boek uit de database.

### Stap 5: Models maken
Maak models voor auteurs en boeken.

#### Commandos om de models aan te maken:
```bash
php artisan make:model Author -m
php artisan make:model Book -m
```
#### Definieer de relatie in het `Author` model:
- Een auteur heeft meerdere boeken (`hasMany` relatie).

#### Definieer de relatie in het `Book` model:
- Een boek behoort tot een auteur (`belongsTo` relatie).

