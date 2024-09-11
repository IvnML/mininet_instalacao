# mininet_instalacao - tutorial para instalação do mininet.
Se você estiver executando uma versão recente do Ubuntu, ou Debian 11+, você pode instalar os pacotes Mininet. 
Note que isso pode dar-lhe uma versão mais antiga do Mininet, mas pode ser muito Uma maneira conveniente de começar.

### Dados do Sistema Operacional utilizado.
> [!NOTE]
> O presente tutorial foi executado em um sistema operacional:
> 
> Kernel: 5.15.0-91-generic x86_64 bits: 64 compiler:
> gcc v: 11.4.0 Desktop: Cinnamon 6.0.4
> tk: GTK 3.24.33 wm: muffin vt: 7 dm: LightDM 1.30.0
> 
> Distro: Linux Mint 21.3 Virginia
> base: Ubuntu 22.04 jammy

## 1. Para confirmar qual versão do sistema operacional você está executando, execute o comando

    lsb_release -a

## 2. Em seguida, instale o pacote base Mininet inserindo apenas um dos seguintes comandos, correspondente à distribuição que você está executando:

    Mininet 2.3.0 on Debian 11: sudo apt-get install mininet
    Mininet 2.2.2 on Ubuntu 20.04 LTS: sudo apt-get install mininet
    Mininet 2.2.2 on Ubuntu 18.04 LTS: sudo apt-get install mininet

## 3. Se não for óbvio qual versão Mininet você tem, você pode tentar:

    mn --version

## 4. O Mininet suporta vários switches e controladores OpenFlow. Para este teste, usaremos o Open vSwitch no modo ponte/standalone.
Para testar isso, tente:

    sudo mn --switch ovsbr --test pingall

## 5. Se o Mininet reclamar que o Open vSwitch não está funcionando, verifique se ele está instalado e em execução:

    sudo apt-get install openvswitch-switch
    sudo service openvswitch-switch start

## 6. Se você deseja passar pelo passo a passo da Mininet, você vai querer instalar software adicional. Os seguintes comandos

    git clone https://github.com/mininet/mininet
    mininet/util/install.sh -fw

irá instalar o switch de referência OpenFlow, controlador de referência e dissector Wireshark.

> [!NOTE]
> Meu SO não tem compatibilidade com pacotes adicionais, logo, instalarei versão do Ubuntu para realizar a instalação completa.


<!--
Tutorial de instalação do Mininet seguindo a documentação apresentada em www.mininet.org. 

Há algumas maneiras de realizar a instalação do mininet, este tutorial utiliza a instalação nativa em um sistema operacional Linux.
Esta opção funciona bem para máquina virtual (VM) local, remote EC2, e instalação nativa. Para tal, necessita-se de uma instalação prévia do Ubuntu, Debian, ou (Experimentalmente) Fedora.
Recomenda-se os mais recentes lançamentos do Ubuntu ou Debian, porque eles incluem versões mais recentes do Open vSwitch. (Fedora também inclui lançamentos recentes do OvS.)

### 1.Para instalar nativamente a partir do código, primeiro você precisa obter o código fonte:

```
git clone https://github.com/mininet/mininet
```

> [!NOTE]
> Note-se que o comando acima irá verificar o mais recente e melhor Mininet (o que é recomendado!). Porém, Se você quiser executar a última versão marcada / lançada de Mininet - ou qualquer outra versão - você pode verificar essa versão explicitamente:

```
cd mininet
git tag  # list available versions
git checkout -b mininet-2.3.0 2.3.0  # or whatever version you wish to install
cd ..
```

### 2.Depois de ter a árvore de origem, o comando para instalar o Mininet é:

```
mininet/util/install.sh [options]
```

> [!TIP]
> No comando *install.sh*, as opções incluem:

* -a: instale tudo o que está incluído no Mininet VM, incluindo dependências como o Open vSwitch, bem como as adições como o dissector OpenFlow wireshark e POX. Por padrão, essas ferramentas serão construídas em diretórios criados em seu diretório doméstico.
* -nfv: instalar Mininet, o switch de referência OpenFlow e Open vSwitch
* -s mydir: use esta opção antes de outras opções para colocar árvores de origem/construir em um diretório especificado em vez de no diretório inicial.

> [!WARNING]
> Então, você provavelmente vai querer usar um (e apenas um) dos seguintes comandos:

* Para instalar tudo (usando diretório local):

```
install.sh -a

```

* Para instalar tudo (usando outro diretório):

```
install.sh -s mydir -a
```

* Para instalar Mininet + user switch + OvS (usando o diretório home):

```
install.sh -nfv
```

* Para instalar Mininet + user switch + OvS (usando outro diretório):

```
install.sh -s mydir -nfv
```

Você pode descobrir sobre outras opções úteis (por exemplo, instalar o dissector OpenFlow wireshark, se ele ainda não está incluído na sua versão do wireshark) usando o wireshark

```
install.sh -h
```

### 3.Após a conclusão da instalação, teste a funcionalidade básica da Mininet:

```
sudo mn --switch ovsbr --test pingall
```
-->























