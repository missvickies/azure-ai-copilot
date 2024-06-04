# azure-ai-copilot
A custom co-pilot using microsoft azure open ai and cosmos DB


# CRUD Operation Examples

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



