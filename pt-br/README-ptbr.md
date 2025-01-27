
---

# Instalação do Kali Linux no WSL com Interface Gráfica

Este guia descreve como instalar o **Kali Linux** no Windows Subsystem for Linux (WSL), configurar a interface gráfica e habilitar acesso remoto.

---

## Pré-requisitos

- Windows 10 (build 19041 ou superior) ou Windows 11
- Permissão para executar o PowerShell como administrador

---

## Passos de Instalação

### 1. Habilitar o WSL

1. Abra o **PowerShell** como administrador.
2. Execute o comando:

   ```bash
   wsl --install
   ```

3. Reinicie o computador.

### 2. Instalar o Kali Linux

1. Após reiniciar, execute o seguinte comando no **PowerShell**:

   ```bash
   wsl --install kali-linux
   ```

2. Ao final da instalação, você será solicitado a criar um usuário UNIX:

   ```bash
   Enter new UNIX username: celo
   ```

3. Defina uma senha para o usuário e confirme:

   ```bash
   New password:
   Retype new password:
   ```

4. Se tudo estiver correto, você verá a mensagem:

   ```bash
   Installation successful!
   ```

---

## 3. Atualizar Pacotes e Instalar Interface Gráfica

### 3.1 Atualizar os Pacotes

1. Entre no sistema como root:

   ```bash
   sudo apt update
   ```

2. Atualize os pacotes instalados:

   ```bash
   sudo apt upgrade -y
   ```

### 3.2 Instalar a Interface Gráfica XFCE

1. Instale o ambiente gráfico:

   ```bash
   sudo apt install kali-desktop-xfce -y
   ```

2. Instale o XRDP para habilitar acesso remoto:

   ```bash
   sudo apt install xrdp -y
   ```

3. Instale dependências adicionais para o acesso remoto:

   ```bash
   sudo apt install -y dbus-x11
   ```

4. Inicie o serviço XRDP (você precisará executar este comando sempre que reiniciar a máquina):

   ```bash
   sudo /etc/init.d/xrdp start
   ```

---

## 4. Configurar o Acesso Remoto

1. Descubra o endereço IP da máquina WSL usando:

   ```bash
   ifconfig
   ```

   Exemplo de saída:

   ```bash
   inet 192.168.1.1  netmask 255.255.255.255  broadcast 192.168.1.1
   ```

2. Copie o endereço exibido após `inet` (no exemplo, **192.168.1.1**).

3. No Windows:
   - Pressione `Win + R`.
   - Digite `mstsc` e clique em **OK**.
   - Cole o endereço IP e conecte.

4. Faça login com o usuário e senha criados anteriormente.

---

## 5. Resultado Final

Se todas as etapas forem seguidas corretamente, você terá o **Kali Linux** instalado e configurado no WSL com interface gráfica e acesso remoto.

---
## 6. Creditos




  [Kali Linux Docs](https://www.kali.org/docs/).
  
  [Kali Linux xfce](https://www.kali.org/docs/general-use/xfce-with-rdp/).
  
  [Thaly Lima](https://www.instagram.com/th4litalima?igsh=MW9hZ2Exc2sxbm4zeQ==).

---