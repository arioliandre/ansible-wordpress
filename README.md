# Deploy de WordPress com Ansible + Vagrant

Projeto experimental de IaC (Infra as Code). Provisionamento de duas VMs com Vagrant, de um servidor de aplicação (WordPress) e outro servidor de banco de dados (MySQL).

Todas as configurações, em ambos os servidores, foram configurados utilizando o Ansible possibilitando a automatização de todo o procedimento. Este procedimento todo, que pode chegar até 1 hora se feito de forma manual, é realizado em poucos segundos devido a automatização.
Ainda há a possibilidade de customização das configurações feitas, não sendo engessado para futuros updates que possam ocorrer no ambiente.

Com algumas alterações é possível alterar a aplicação para um sistema da sua preferência, e a utilização de outro banco de dados, como o MongoDB, por exemplo.

Pré-requisitos para rodar o projeto:

- Ansible 2.9
- Vagrant 2.2
- Sistema Operacional Linux ou MacOS

Obs: não há nenhuma versão para utilização do Ansible em Windows.

# Passo-a-passo para instalação (Linux Ubuntu)

<a href="https://www.ansible.com/resources/get-started">Ansible</a>
```
Abra o terminal e digite: sudo-apt get ansible
```
<a href="https://www.vagrantup.com/downloads.html">Vagrant</a>
```
Acesse o site do Vagrant e realizado o download correspondente ao seu Sistema Operacional.
```
<a href="https://www.virtualbox.org/">VirtualBox</a>
```
Acesse o site do VirtualBox e realize o download correspondente ao seu sistema Operacional.
```
# Realizando o clone do projeto
```
git clone git@github.com:arioliandre/ansible-wordpress.git ou git clone https://github.com/arioliandre/ansible-wordpress.git
```

# Executando o projeto

Após realizar o clone do projeto e instalar todas as ferramentas citadas, acesse o diretório com o projeto e abra o terminal. No terminal:

<h5> Provisionando os servidores </h5>

```
vagrant up
```

<h5> Iniciando o playbook do Ansible </h5>

```
ansible-playbook provisioning.yml -i hosts 
```

<h5> Acessando as VMs por SSH </h5>

```
vagrant ssh wordpress
vagrant ssh mysql
```

Após o start e conclusão do playbook, você pode acessar diretamente do seu navegador o endereço: http://172.17.177.40/.

A tela de instalação da aplicação (WordPress) será exibida.

----

# Documentações oficiais

<a href="https://www.vagrantup.com/docs">Vagrant</a>

<a href="https://docs.ansible.com/">Ansible</a>
