```dart
import 'package:appwrite/appwrite.dart';

void main() { // Init SDK
  Client client = Client();
  Databases databases = Databases(client);

  client
    .setEndpoint('https://[HOSTNAME_OR_IP]/v1') // Your API Endpoint
    .setProject('5df5acd0d48c2') // Your project ID
  ;
  Future result = databases.listDocuments(
    databaseId: '[DATABASE_ID]',
    collectionId: '[COLLECTION_ID]',
  );

  result
    .then((response) {
      print(response);
    }).catchError((error) {
      print(error.response);
  });
}
```