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

Vamos a intentar la máquina Perfection

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/6dc2ac63-2ff3-4fb4-b0a6-cfe3ce2a2d0a)

Realizamos un escaneo

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/f0373507-482a-4169-a416-b83e7219b7f3)

Descubrimos que están abiertos los puertos 80 y 22 con tcp

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

Intentamos injectar código con Burp Suite a la página

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/6f215f81-4dbe-4de8-ba33-4978d21e274b)

Y obtenemos algo raro

![image](https://github.com/Z4ND3RX/EAM-HACK-THE-BOX/assets/106892676/c6b180d3-2fd9-40ad-9be4-7edac6fd6773)

Y la verdad ya no sé que hacer ☹ hasta aquí llegó el bus
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


