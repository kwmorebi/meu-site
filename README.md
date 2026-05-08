"Projeto - Infraestrutura como Código com Vagrant"

## Este projeto tem como objetivo automatizar a criação e configuração de uma máquina virtual utilizando o Vagrant. A VM foi configurada sem a necessidade de acessar o VirtualBox.
Durante a configuração foram realizados:

Criação da máquina virtual com Vagrant
Configuração de IP privado
Compartilhamento de pastas entre host e VM
Instalação e configuração do Apache
Configuração de acesso SSH
Redirecionamento de portas


## Como subir a VM
É necessário ter instalado: Vagrant, Git e Visual Studio Code

## Passos para configuração
Acesse o terminal e digite: mkdir 'meu-site'
Vá para esse diretório: 'cd meu-site'
Dê o comando 'vagrant up' para iniciar a máquina

## Acessar site
http://192.168.0.2 ou http://localhost:8080

## Subir, Recarregar e Destruir a VM
vagrant up
vagrant reload
vagrant halt

## Acessar SSH e Status
vagrant ssh
vagrant status

## Tecnologias
Vagrant, VirtualBox, Linux, Apache2, SSH, rede privada e port forwarding.

## Observações
Feito por Juliana Felix.