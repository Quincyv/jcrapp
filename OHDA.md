Na een Docker build verwachten we een website die een tekst geeft. 
A:
docker build . -t jcr-app
docker run jcr-app

O:
Error: Cannot find module '/usr/src/app/app.js'

H:
iets niet goed meegekomen in het build proces
D: 
In de container kijken.
A: 
docker run -it --entrypoint=/bin/bash jcr-app
en dan in de shell ls

O: Daar is dus geen app.js
H: zou via de COPY . /usr/src/app/ mee moeten komen.
H: zou app.js wel in bron directory staan?
O: nee dus
H: we kunnen de bron dir of de CMD aanpassen.
D: CMD aanpassen
A: CMD ["node", "jcr.js"] en nieuwe build

O: docker run jcr-app                           
Server is running on port 80

Safari cannot connect to localhost:80
H: 80 is een priviliged port
D: portmapping
A:
docker run -p3000:80 jcr-app

O:
 % curl localhost:3000
Joint Cyber Range%                    

FTW

