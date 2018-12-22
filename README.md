# InMemoryCache-Using-Redis
InMemoryCache Using RedisDb


Steps To Test InMemoryCache Applications

1 . Run Mongodb Server

Run below command
  Example
      bin/mongod --directoryperdb --dbpath /Users/amlanmohanty/Documents/Servers/mongodata/db

2. Run Redis InMemory Server

  Run below command
      Example
          bin/redis-server


3. Run InMemoryCache microservice Applications

java -jar  InMemoryCache-0.0.1-SNAPSHOT.jar


----Insert some data to Mongodb----

curl -X PUT "http://localhost:8000/hospital/doctor/set" -H 'Content-Type: application/json' -d'
{

	"id":"101",
	"doctorName": "Ram",
	"doctorSpeciality": "Nero surgial",
	"doctorStatus":"On Today"
}
'

curl -X PUT "http://localhost:8000/hospital/doctor/set" -H 'Content-Type: application/json' -d'
{

	"id":"102",
	"doctorName": "Shyam",
	"doctorSpeciality": "Heart surgial",
	"doctorStatus":"Off Today"
}




---GET Doctors by Id---

http://localhost:8000/hospital/doctor/get/101

http://localhost:8000/hospital/doctor/get/102


Testing 

When "method /get/{doctorId} from mongodb executed "+Id  statement showing in console data is comming from Mongodb.
other wise data is comming from redis inMemory server.
