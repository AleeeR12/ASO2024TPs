TP5
Realizado por: Russo Alexia y Zubiel Micaela

Parte 1:
1. El script comienza con un mensaje de bienvenida.

![Screenshot_1](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/3fdaf418-faa6-42a0-887e-302da53dd676)

2. El juego se ejecuta dentro de un bucle while que permite repetir el juego mientras el usuario desee continuar.
   
![Screenshot_2](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/20609f4c-8c35-4a29-ae47-2f2231f5ed66)

3. Se solicita al usuario que elija entre piedra, papel o tijera.
   
![Screenshot_3](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/2af79bcc-ec57-46d4-9624-3c544aab6e03)

4. La computadora hace una elección aleatoria entre piedra, papel o tijera.

![Screenshot_4](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/37458bfd-fc38-4d40-9045-d8d73849a731)

5. Se compara la elección del usuario con la de la computadora para determinar el ganador o si hay un empate.

![Screenshot_5](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/af9b6ca8-fad4-4dc4-ac56-1b96e6153ae0)

6. Se le pregunta al usuario si quiere jugar de nuevo.

![Screenshot_6](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/ca3a9a1b-c5d9-467f-b9c0-f529839da8de)

7. Si el usuario decide no jugar más, se muestra un mensaje de despedida.

![Screenshot_7](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/28257fe1-4924-457c-b55e-8b6a541bd6bd)

Como ejecutar el Script: 
1. Guarda el contenido del script en un archivo con extensión .sh, por ejemplo, piedra_papel_tijera.sh.
   
2. Abre una terminal y navega al directorio donde guardaste el archivo. Luego, da permisos de ejecución al archivo usando el siguiente comando:
```
chmod +x piedra_papel_tijera.sh
```
3. Ejecuta el script en la terminal con el siguiente comando:
```
./piedra_papel_tijera.sh 
```


Parte 2:

1. La clave API necesaria para autenticar las solicitudes a WeatherAPI se define como una variable. 

![Screenshot_1](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/02ddf55f-683c-47ff-b41d-b0c62a86b873)

2. Verifica si se proporcionó una ciudad como argumento al script. Si no se proporciona, muestra un mensaje de uso y termina el script
 
![Screenshot_2](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/a1699146-e099-4ca6-855f-b94be383fb04)

3. Almacena el primer argumento (la ciudad) en una variable.

![Screenshot_3](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/51074b46-16a5-4fc0-973c-0322707637e4)

4. Construye la URL para realizar la solicitud a la API de WeatherAPI, incluyendo la clave API y la ciudad especificada.

![Screenshot_4](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/80a75d57-1115-4b8a-a389-38709f5317b7)

5.Utiliza curl para hacer una solicitud HTTP GET a la URL construida y almacena la respuesta en una variable.

![Screenshot_5](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/efef266f-5c55-47dd-826c-8b0ff23e1d8a)

6. Verifica si la respuesta contiene un mensaje de error. Si es así, muestra un mensaje de error y termina el script.

![Screenshot_6](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/eec72f63-e747-4f62-9a21-0fde218ba086)

7. Utiliza jq para extraer la temperatura actual, la condición y la humedad de la respuesta JSON.

![Screenshot_7](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/c338b5cc-984d-4c87-b335-d7f8948984ed)

8. Imprime la información del clima en la terminal.

![Screenshot_8](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/90a2d005-43ed-4227-ae38-ee15780c5a01)


Como ejecutar el script: 
1. Guarda el contenido del script en un archivo con extensión .sh, por ejemplo, clima.sh.

2. Abre una terminal y navega al directorio donde guardaste el archivo. Luego, da permisos de ejecución al archivo usando el siguiente comando:
```
chmod +x clima.sh
```
3. instalar "jq" en caso de no tenerlo para procesar JSON. codigo para instalarlo:
```
sudo apt-get update
sudo apt-get install jq
jq --version
```
4. Ejecuta el script proporcionando el nombre de una ciudad como argumento. Por ejemplo:
```
./clima.sh "Buenos Aires"
```
