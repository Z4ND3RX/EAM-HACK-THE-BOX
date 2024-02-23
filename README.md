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
