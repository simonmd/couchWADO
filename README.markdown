#couchWADO#


##A DICOM WADO server in CouchDB v0.0##


**Requeriments**

* CouchDB. If you are a MAC user download and install CouchDBX from http://www.couch.io/get

**Instructions**

* In a browser open http://127.0.0.1:5984/_utils 
* In the Futon interface go to Configuration link in the Tools Menu
* In the section httpd change the bind_address parameter to 0.0.0.0
* Go to The Overview page and create a new database
* Go to Replicator link in the Tools Menu
* In the REPLICATE CHANGES FROM section select Remote database and type http://couchwado.couchone.com/couchwado if you want replicate the database without sample documents or type http://couchwado.couchone.com/couchwado-plus-images if you want replicate the database with the sample DICOM documents (You can replicate the database without Documents and insert your own Documents with the couchDICOM script: https://github.com/simonmd/couchdicom )
* In the TO section select Local database and select the database created above
* Click on Replicate button
* After the replication go to the _design/* documents in your database and change the var url in the list section to http://localhost:5984/yourDatabaseName/ (Do not forget the last slash (/) in the url variable)
* Go to http://localhost:5984/yourDatabaseName/_design/patient/_list/patient_list/patients?group=true
* Enjoy couchWADO
