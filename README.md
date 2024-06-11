# azure-ai-copilot
This is part of phase 1 of the microsoft AI hackation. A custom co-pilot using microsoft azure open ai and cosmos DB. This code includes loading product data and creating embeddings to implement vector search. Openai and langchain are then used to create dialogue for the backend API (hosted in azure). The frontend of this application is deployed from a .bicep file following the developers guide from the hackathon.

![screenshot](./Screen_Shot.png)

# CRUD Operation Examples - loading data

creating a document
```
const result = await products.insertOne(product);
console.log(`A product was inserted with the _id: ${result.insertedId}`);
```

reading a document
```
const product = await products.findOne({ _id: '2BA4A26C-A8DB-4645-BEB9-F7D42F50262E' });
console.log("Found the product:", product);
```
update a document
```
const options = { returnDocument: 'after' };
const updated = await products.findOneAndUpdate(
    { _id: '2BA4A26C-A8DB-4645-BEB9-F7D42F50262E' },
    { $set: { price: 14242.42 } },
    options);
```
delete a document
```
const result = await products.deleteOne({ _id: '2BA4A26C-A8DB-4645-BEB9-F7D42F50262E' });
console.log(`Number of documents deleted: ${result.deletedCount}`);
```



