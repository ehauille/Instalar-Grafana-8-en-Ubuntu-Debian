# Instalar-Grafana-8-en-Ubuntu | Debian


# Actualizar el sistema
    sudo apt-get update
    sudo apt-get upgrade
    sudo reboot
    
# Añadir repositorio APT Grafana 8
- Agregue la clave gpg de Grafana que le permite instalar paquetes firmados.

    sudo apt-get install -y gnupg2 curl
    curl https://packages.grafana.com/gpg.key | sudo apt-key add -
    
- instale el repositorio APT de Grafana 8
    sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"

# Una vez que se agregue el repositorio, proceda a actualizar sus repositorios Apt e instale Grafana 8 en Ubuntu / Debian.
    sudo apt-get update
    sudo apt-get -y install grafana
    
- Inicie el servicio de grafana
    sudo systemctl start grafana-server

- Asegúrese de que el servicio está configurado para ejecutarse en el arranque.
    sudo systemctl enable grafana-server

- Para verificar el estado del servicio
    systemctl status grafana-server
    
# Una vez iniciado el servicio, puede acceder a su panel web visitando la IP del servidor en el puerto 3000. Si tiene un firewall activo, principalmente ufw, permita el puerto 3000 en el firewall.
    sudo ufw allow proto tcp from any to any port 3000

# Los inicios de sesión son predeterminados, (Pero debe cambiar inmediatamente después de autenticarse.):

    Usuario: admin
    Contraseña: admin

