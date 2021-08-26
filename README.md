# MongoDb_comands

### Criando o database

```
use reprograma_larisse
```

### Criando uma collection

```
db.createCollection('Banco')
```

### Inserindo documentos

```
db.Banco.insert({
    "esportes" : { 
            "categoria": "Natação", 
            "pais": "Brasil",
            "medalhas": "17",
    },
    "atleta": {
            "nome": "Poliana Okimoto",
	    "ano": 2016,
	    "tipo": "10 km - maratona aquatica"
    },
    "medalha": "Bronze",
    "RIO 2016": true
})
```

```
db.Banco.insert({
    "esportes" : { 
            "categoria": "Ginástica", 
            "pais": "Brasil",
            "medalhas": "6",
    },
    "atleta": {
            "nome": "Rebeca Andrade",
	    "ano": 2020,
	    "tipo": "solo"
    },
    "medalha": "Ouro",
    "tokio2020": false
})
```

```
db.Banco.insert({
    "esportes" : { 
            "categoria": "Surf", 
            "pais": "Brasil",
            "medalhas": "1",
    },
    "atleta": {
            "nome": "Ítalo Ferreira",
	    "ano": 2020,
	    "tipo": "livre"
    },
    "medalha": "ouro",
    "tokio2020": true
})
```

### Deletando documentos (pela esportes)

```
db.Banco.remove({"esportes.categoria": /.*PolianaOkimoto.*/})
```

### Consulta com projeção

```
db.getCollection('Banco').find({},{"atleta" : 1, "_id" : 0})
```

### Consulta utilizando combinação entre os seletores

```
db.getCollection('Banco').find({$or:[{"esportes.pais": /.*Brasil.*/},{tokio2020: true}]})

```

### Consulta ordenada

```
db.getCollection('Banco').find().sort({"atleta.categoria": 1})

```

