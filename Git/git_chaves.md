## Criando par de chaves 

> Essas chaves são úteis para permitir a comunicação/sincronização de um repositório local com repositório remoto como github, gitlab, bitbucket etc. 

### Windows  

> No windows é recomendado baixar o [git bash](https://git-scm.com/) depois que instalar execute o comando abaixo para criar o par de chaves 

```shell 
$ ssh-keygen -t rsa -C "email@provedor.com" -b 4096
```

> Depois de executar o comando serão criadas um par de chaves geralmente na pasta home do usuário. Obs: O diretório criado fica com atributo oculto.

No windows va em executar (tecla Windows+R) digite ***%USERPROFILE%\\.ssh*** clique em ***OK***. Ao executar o comando acima caso não escolha alterar o nome dos arquivos, dentro da pasta terá o arquivo ***id_rsa*** e ***id_rsa.pub***. No arquivo ***id_rsa.pub*** está a chave pública que deve ser cadastrada no repositório remoto.

## Linux

No linux o comando é o mesmo, o par de chaves por padrão também fica na pasta home do usuário 

```sh 
$ ls -la /home/usernam/.ssh

$ cat /home/usernam/.ssh/id_rsa.pub
```

