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

## Stappenplan:

### Stap 1: Migraties maken
Maak migraties voor de auteurs en boeken tabellen.

1. **Commandos** om de migraties aan te maken:
   ```bash
   php artisan make:migration create_authors_table --create=authors
   php artisan make:migration create_books_table --create=books
