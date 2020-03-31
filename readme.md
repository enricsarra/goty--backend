# Goty-backend: 
Proyecto firebase: 
- **firestore-grafic-vote**
- S'utiliza a goty [https://github.com/enricsarra/goty]
- utilitzo Postman per provar
- no pujem el directori "environments". (Veure gitignore).
# Objectiu: 
Montar servidor rest a "Functions " que permeteix fer peticions a Firebase y actualizar la db a Cloud Firestore.
# Com s'ha creat
- crear carpeta "goty-backend"
- Seleccionar a consola Firestore "Functions" y començar
- Veure guía de introducció para a més info.
- "sudo npm install -g firebase-tools"   
- accedir al directori creat
- "firebase login" 
- "firebase init"    (seleccionar "Functions" y "Use an existing project" , "typescript" , "tslint", "install dependencies with npm now (així ja s'instala **firebase-admin y firebase-functions**).
- Es creen els fitxers a la carpeta 
- modificar **index.ts** treure els comentaris
- **firebase deploy** (puja la carpeta  **lib ** que no es s´ha de modificar).
 - Anotar deprés de  **Deploy complete!** 
 - Function URL (helloWorld): https://us-central1-firestore-grafic-vote.cloudfunctions.net/helloWorld
- Project Console: https://console.firebase.google.com/project/firestore-grafic-vote/overview

- provar al navegador la "Function URL" o al Postman

# Començar a treball  local
- cd goty-backend
- firebase serve
- anotar "http function initialized" (http://localhost:5000/firestore-grafic-vote/us-central1/helloWorld)
- Indicar a typescript que compile a javascript. 
- Compilar :
- Obrir terminal 
- Opció-1
   - cd /functions
   - npm run build  (compila a **lib** definida a **"outDir": "lib"** de tsconfig.json) 

- Opció-2
   - cd /functions
   - tsc --watch    (compila cada vegada que modifiquem códi)
# Firebase per trabaallar localment 
- https://firebase.google.com/docs/admin/setup?authuser=0
- Amb local (development)
        - Anar a **Configuracion/Cuentas de servicio** i asegurarse que el **Fragmento de configuración del SDK de administración** es "Node.js". 
 - Generar clau privada. Es genera un fitxer json. Canviar el nom del fitxer (es opcional) a **serviceAccountKey.json** i copiar a la carpeta **src** i a **lib** . Guardar aquest fitxer  a un lloc segur.
- modificar **index.ts** per importar **firebase-admin**, **serviceAccount** e **inicializar admin**.
 - definim un "servidor express "
- **cd function**  (important)
 - **npm install express cors --save-dev**
 - **npm install @types/cors --save-dev**  
 - El tipat ajuda a typescript amb les llibreries de javascript

# Deploy (producció)
    -  cd goty-backend 
    -  firebase deploy 
    - anotar  functions[...]: httpsL//....
    - Probar

       