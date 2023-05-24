# SOCKETS-CLIENT
La parte inicial es similar a la del servidor 

## OJO:
Para codificar un mensaje es de la forma : 

    data = sock.sendall(msg.encode("utf-8"))  # se usan comillas dobles ("") o puede ser con comillas simples ('')
    
Para decodificar un mensaje es de la forma:

     sock.recv(msg.decode('utf-8))  #se usan comillas simples ('')
    
   ---------------------------
   
   
   import socket


    sock_buffer = 1024


    if __name__ == '__main__':
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        server_address = ("192.168.0.25", 5000) #se debe cambiar si se usa en otra computadora

        print(f"Conectando a {server_address[0]}:{server_address[1]}")

        sock.connect(server_address)  #se enlaza ip y puerto para conectarnos a un servidor
     
     
  En este caso se usa `sock.connect(server_address)` a diferencia de un servidor, en el cual se usaba `sock.bind(server_address)`. 


        try: 
            msg = "Hola mundo"
        
        
  Se envia el mensaje codificandolo en binario:

            sock.sendall(msg.encode("utf-8"))   
            
 La siguiente linea de comando se encarga de recibir datos del socket utilizando el método recv.

sock_buffer es un parámetro que indica el tamaño máximo de los datos que se pueden recibir en una única llamada a recv.

            data = sock.recv(sock_buffer)

            print(f"Recibi {data.decode('utf-8')}")


        finally : 
            print("Cerrando conexion")
            sock.close()
            
  Finalmente se termina la conexion con el servidor.

    
