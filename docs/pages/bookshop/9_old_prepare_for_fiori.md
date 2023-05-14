# Prepare your project for production



###  Add additional sample data

Add missing sample data. 

1. Download all sample data from the [cap/samples](https://github.com/SAP-samples/cloud-cap-samples/tree/main/bookshop/db/data) repository.


   ```Shell
   sap.capire.bookshop-Authors.csv
   sap.capire.bookshop-Books.csv
   sap.capire.bookshop-Genres.csv
   ```

2. Copy them into the project folder `db/data`. Replace the old ones.
   Note, it is important that the name matches the name space which your defined in schema.cds: `sap.capire.bookshop`.  <br>

3. Explore the new content of the service with `cds watch` in terminal.


### Add approuter and authorization for production

1. Open your bookshop project terminal.

2. Run the command 

   ```
   cds add approuter --for production
   ```

   This will add the features 'xsuaa' and 'approuter'. You don't need to run the script `cds add xsuaa` in addition.

3. In **mta.yaml** you get the new dependency 

   ```
   requires:
      - name: bookshop-auth
   ```
   
   and two new modules:
   - name: bookshop
   - name: bookshop-auth
    
4. In **package.json** of your bookshop project, you get 2 new dependencies:
   
   ```json
   "dependencies": {
     "@sap/xssec": "^3",
     "passport": "^0"
    ```
   
   In the "cds" definition, you get also a new entry:
   
   ```json
   "cds": {
      "requires": {
         ....
         "[production]": {
           "db": "hana-cloud",
           "auth": {
              "kind": "xsuaa"
           }
         }
      }
    }  
    ```

5. You get also a new file **xs-security.json** in your bookshop project. 
   It contains Authorization [scopes](https://help.sap.com/docs/SAP_HANA_PLATFORM/4505d0bdaf4948449b7f7379d24d0f0d/3bfb120045694e21bfadb1344a693d1f.html?locale=en-US), Attributes and Role templates and is initial for now:

   ```json
   {
     "scopes": [],
     "attributes": [],
     "role-templates": []
   }
   ```
   
   The file is the configuration for the BTP Authorization and Trust Management Service and will be store in the CF Space instance `bookshop-auth`.
   
6. In the application itself you get 2 new files:
   
   - app/package.json with the approuter dependencies and  
   - app/xs-app.json which contains the approuter rules

7. Run `npm i` to add the new dependencies to your bas project.

8. Run `cds env get requires.auth`to see what you have configured.

9. For development purposes you can switch off authentication in file **"package.json"** as long as you dont have implemented authentication. 

   ```json
   "cds": { 
     "requires": {
       ....
       "auth": { "kind": "dummy" }
     }
   }
   ```

   For more information, see [Authentication Strategies](https://cap.cloud.sap/docs/node.js/authentication#strategies).



Congratulations! You have finished this tutorial!

