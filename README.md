# DogPark
Contest entry for #AWSDeepLensChallenge

This contest entry uses the deeplens-hotdog-no-hotdog model and the DogPark lambda function as part of the deep lens project. 
This project is deployed to deep lens. The DogParkNotifier lambda function receives MQTT message data from deep lens, parses the 
fields using an SQL statement:

Rule query statement: SELECT key, dog1Label, dog1Prob, dog2Label, dog2Prob, URL FROM '$aws/things/deeplens_xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx/infer'

DogParkNotifier formats the message and sends it to SNS either for SMS text messages delivery, or email.
