

---

# Instalación de Kali Linux en WSL con Interfaz Gráfica

Esta guía describe cómo instalar **Kali Linux** en el Windows Subsystem for Linux (WSL), configurar la interfaz gráfica y habilitar el acceso remoto.

---

## Requisitos Previos

- Windows 10 (build 19041 o superior) o Windows 11
- Permiso para ejecutar PowerShell como administrador

---

## Pasos de Instalación

### 1. Habilitar WSL

1. Abra **PowerShell** como administrador.
2. Ejecute el siguiente comando:

   ```bash
   wsl --install
   ```

3. Reinicie el equipo.

### 2. Instalar Kali Linux

1. Después de reiniciar, ejecute el siguiente comando en **PowerShell**:

   ```bash
   wsl --install kali-linux
   ```

2. Al final de la instalación, se le pedirá que cree un usuario UNIX:

   ```bash
   Enter new UNIX username: celo
   ```

3. Defina una contraseña para el usuario y confirme:

   ```bash
   New password:
   Retype new password:
   ```

4. Si todo está correcto, verá el siguiente mensaje:

   ```bash
   Installation successful!
   ```

---

## 3. Actualizar Paquetes e Instalar Interfaz Gráfica

### 3.1 Actualizar los Paquetes

1. Inicie sesión como root:

   ```bash
   sudo apt update
   ```

2. Actualice los paquetes instalados:

   ```bash
   sudo apt upgrade -y
   ```

### 3.2 Instalar la Interfaz Gráfica XFCE

1. Instale el entorno gráfico:

   ```bash
   sudo apt install kali-desktop-xfce -y
   ```

2. Instale XRDP para habilitar el acceso remoto:

   ```bash
   sudo apt install xrdp -y
   ```

3. Instale dependencias adicionales para el acceso remoto:

   ```bash
   sudo apt install -y dbus-x11
   ```

4. Inicie el servicio XRDP (deberá ejecutar este comando cada vez que reinicie la máquina):

   ```bash
   sudo /etc/init.d/xrdp start
   ```

---

## 4. Configurar el Acceso Remoto

1. Descubra la dirección IP de la máquina WSL utilizando:

   ```bash
   ifconfig
   ```

   Ejemplo de salida:

   ```bash
   inet 192.168.1.1  netmask 255.255.255.255  broadcast 192.168.1.1
   ```

2. Copie la dirección que aparece después de `inet` (en el ejemplo, **192.168.1.1**).

3. En Windows:

   - Presione `Win + R`.
   - Escriba `mstsc` y haga clic en **OK**.
   - Pegue la dirección IP y conéctese.

4. Inicie sesión con el usuario y la contraseña creados anteriormente.

---

## 5. Resultado Final

Si todos los pasos se siguen correctamente, tendrá **Kali Linux** instalado y configurado en WSL con interfaz gráfica y acceso remoto.

---

## 6. Créditos

[Documentación de Kali Linux](https://www.kali.org/docs/).

[Kali Linux xfce](https://www.kali.org/docs/general-use/xfce-with-rdp/).

[Thaly Lima](https://www.instagram.com/th4litalima?igsh=MW9hZ2Exc2sxbm4zeQ==).

---

