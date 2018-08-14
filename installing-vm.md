## Instalando a máquina virtual com Windows 10 no ubuntu para testar a assinatura no monolito

### Instalando a virtualbox

Adicione a linha a seguir no final do seu `/etc/apt/sources.list` mudando para a distribuição do ubuntu que você usa.

```
deb https://download.virtualbox.org/virtualbox/debian <mydist> contrib

Ex:

deb https://download.virtualbox.org/virtualbox/debian xenial contrib

```

A seguir em seu terminal ubuntu, faça o download e registre a apt-secure key publica do oracle para o download

```
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
```

E a seguir instale o virtualbox

```
sudo apt-get update
sudo apt-get install virtualbox-5.2
```

### Instalando o windows na máquina virtual
> Em máquinas com processador AMD é necessario ativar na bios o `secure virtual machine` caso queira instalar uma máquina virtual de 64-bit

Acesse o site da microsoft para fazer o download da iso do [windows 10](https://www.microsoft.com/pt-br/software-download/windows10ISO)

Abra o virtual box, clique em `new`, dê um nome a sua máquina virtual, selecione o tipo do sistema operacional e em seguida a versão. No meu caso, windows10(64-bit). Clique em `next`.

Adicione no minímo 2 gb de memoria ram para sua máquina virtual, e a seguir clique novamente em `next`.

Selecione a maneira que criará o seu HD da máquina virtual.
Para o HD eu escolhi as opções a seguir, mas você pode escolher da maneira que achar melhor.

`create a virtual hard disk` -> create -> `VDI(virtual disk image)` -> next -> `dynamically allocated` -> next -> `32 GB` -> create

Após gerar a sua máquina virtual, no aplicativo do virtual box, selecione a máquina virtual que acabou de criar e clique no botão `start`. Selecione a iso do windows que acabou de fazer o download e clique em `start`.

Instale o windows normalmente.

### Instalando Extension Pack

Acesse a página de downloads do [virtual box](https://www.virtualbox.org/wiki/Downloads)

Procure pelo link e baixe o VirtualBox Extension Pack

A seguir inicie sua máquina virtual e clique em `file` -> `preferences`  na barra de opções superior da sua máquina virtal. Clique em `extensions` e em `Add new package`. Selecione o extension pack.

Reinicie sua máquina virtual.

Vá em `devices` -> `Insert guest additions CD Image`.

Em seguida, em seu windows, acesse o file explorer e abra o CD do `virtual box guest additions`

E instale o `VBoxWindowsAdditions`

Reinicie sua máquina virtual.

### Fixando a leitura de USB da máquina virtual.

```
sudo apt update
sudo apt install dkms
sudo apt install gnome-system-tools
```

Pesquise por users no seu ubuntu e abra o `users and groups`

Clique no seu usuario e em seguida em `manage groups`

selecione `vboxusers` e clique em propriedades. Selecione o seu usuário e click em `ok` -> `close` -> `close`

Reinicie seu ubuntu

### Instalando Drivers da leitora de

[Instalação da certificadora digital](https://serasa.certificadodigital.com.br/instalacao/)





Fontes:

[Installing Virtual box on Ubuntu](https://www.virtualbox.org/wiki/Linux_Downloads)

Videos step by step:

[Installing VirtualBox Guest Additions in Windows and Linux](https://www.youtube.com/watch?v=T5jU5i80m-M)

[Fix virtualbox usb recognition](https://www.youtube.com/watch?v=QWsNp33sYqE)




