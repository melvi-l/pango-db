# PangoDB

That was what a startup ask me to do for an internship interview.

Some company have a 6 month turn over of underpaid unqualify developer pressured by business target and ask you to do 6h full stack project with UI mockup, just to ask you to spend 3 more hour live coding in front of totally clueless CEO asking you to implement a week worth of work. Be safe kid.  

The company name is apartoo, glad it did not work out I end up working for a spatial project.

## Setup

1. API
`node ./backend/app.js`
2. Angular
```
cd ./frontend
ng serve
```

## Wording
L'objectif est de créer un mini carnet d'adresse pour "Pangolin" sur Express.js (sous forme d'API) avec un front sur angular &  DB Mongo de préférence. 
- (Inscription/Connexion/Déconnexion) du "Pangolin" par login/mot de passe 
- (Afficher/Modifier) son rôle (Guerrier, Alchimiste, Sorcier, Espions, Enchanteur)
- (Ajouter/Supprimer) en amis un autre "Pangolin" à partir d'une liste des autres Pangolins inscrits.

## Maquette UI 

Voir le figma [ICI](https://www.figma.com/file/UJoRrhzQ8ll8ni7kRAiNi1/PangoDB?type=design&node-id=0%3A1&t=m2YhP6smNUg7kqX0-1)

## API

port: `http://localhost/8080`

Modele: 
Pangolin
```js
type Pangolin = {
    username: {
        type: String,
        required: true,
    },
    password: {
        type: String,
        required: true,
    },
    friend: [{
        type: mongoose.Schema.Types.ObjectId,
        ref: 'User',
    }],
    role: {
        type: String,
        enum: ['Guerrier', 'Alchimiste', 'Sorcier', 'Espion', 'Enchanteur'],
        default: 'Guerrier',
    },  
}
```
### AUTH

- sign up:
POST `/auth/signup` 

- login:
POST `/auth/signup` 


### CREATE (auth)
POST `/pangolin` 

### READ (auth)
findAll:
GET `/pangolin` 

findOne:
GET `/pangolin/:id` 

### UPDATE (auth)
PUT `/pangolin/:id` 

### DELETE (auth)
DELETE `/pangolin/:id`
