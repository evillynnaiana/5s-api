# 5s-api
API desenvolvida em Nest para proporcionar a avaliação de salas/areas por um auditor
### Fundamentos de Sistemas Computacionais

---

## 1. Executando Comandos como Superusuário

```
sudo nome_programa
```

---

## 2. Compressão de Arquivos

### Compactação com `gzip`

```
gzip nome_arquivo
gzip -k nome_arquivo
gzip -f -k nome_arquivo
```

### Visualização de arquivos compactados

```
zcat nome_arquivo
zmore nome_arquivo
gzip -l nome_arquivo
```

### Compactação de múltiplos arquivos

```
gzip arquivo1 arquivo2 arquivo3 ... arquivoN
gzip -k arquivo1 arquivo2 arquivo3 ... arquivoN
gzip -r nome_diretorio/
gzip -r -k nome_diretorio/
```

### Descompactação

```
gzip -d nome_arquivo.gz
gzip -d -k nome_arquivo.gz
```

### Opções para compactação

```
gzip --fast nome_arquivo
gzip --best nome_arquivo
```

### Compactação com `tar`

```
tar cvf arquivo.tar arquivo1 arquivo2 ... arquivoN
gzip sample.tar
tar -zcvf arquivo.tar.gz /home/user/Docs
tar -xvf nome_arquivo.tar
tar -xvf nome_arquivo.tar.gz -C /home/user/
tar -tvf nome_arquivo.tar
tar -rvf nome_arquivo.tar novo_arquivo.txt
tar --delete -vf nome_arquivo.tar deletar_arquivo.txt
```

---

## 3. Usuários, Grupos e Privilégios

### Comandos para obtenção de informações

```
id
groups usuario
users
w
who
whoami
```

### Gerenciamento de permissões

```
chmod [opções] modo_arquivo arquivo
chown novo_dono[.novo_grupo] arquivo
chgrp [opções] novo_grupo arquivo
chattr [opções] operando valor arquivo
lsattr [opções] arquivo
```

### Modificação absoluta de permissões

```
chmod 644 file
```

### Modificação simbólica de permissões

```
chmod g+x arquivo.txt
chmod o-rw+x,u+x arquivo.txt
chmod a-x arquivo.txt
```

### Modificação de proprietário

```
chown nome_novo_usuario nome_arquivo
chown nome_novo_usuario:novo_grupo_usuario nome_arquivo
chown :novo_grupo_usuario nome_arquivo
```

### Links simbólicos

```
ln -s arquivo_fonte_existente.txt link_simbolico
ln -s /mnt/my_drive/projects ~/my_projects
ln -sf arquivo_fonte_existente.txt novo_link
unlink symlink_to_remove
rm symlink_to_remove
find directory -type l ! -exec test -e {} \; -print
find /directory/to/search -xtype l
```

---

## 4. Gerenciamento de Processos

### Comandos úteis

```
top
uptime
free
vmstat
```

### Controle de Tarefas

```
CTRL + C  # Aborta um processo
CTRL + Z  # Suspende um processo
&         # Executa um comando em background
bg        # Move processo para background
fg        # Move processo para foreground
jobs      # Lista processos ativos no shell
```

### Comando `ps`

```
ps x
ps ax
ps u
ps w
ps -A, ps -e, ps -T, ps -a, ps -ef, ps –eF
ps -u nome_usuario
ps -L numero_PID
ps -fG nome_grupo
ps -C nome_processo
ps -fp PID1, PID2, PID3, …., PIDn
ps -fL -C nome_processo
ps -e -o pid,uname,pcpu,pmem,comm
ps -ef | grep nome_processo
```

### Terminando processos

```
kill PID
kill –STOP PID
kill –CONT PID
pkill nome_processo
```

---

## 5. Resolução do Exercício

1) Nenhum arquivo foi identificado como executável, então foram criados três arquivos:

```
touch arquivo_usuario
chmod 700 arquivo_usuario

touch arquivo_grupo
chmod 010 arquivo_grupo

touch arquivo_outros
chmod 001 arquivo_outros
```

2) Permissões para o dono:
```
-rwx------
```
Explicação: O dono pode ler, escrever e executar o arquivo.

3) Permissões para o grupo:
```
------x---
```
Explicação: O grupo pode apenas executar o arquivo.

4) Permissões para outros usuários:
```
-------x
```
Explicação: Outros usuários podem apenas executar o arquivo.

5) Para remover a permissão de gravação do dono:
```
chmod u-w arquivo_usuario
```

6) Criar um diretório dentro da pasta temporária:
```
mkdir /tmp/dados
ls -l /tmp
```

7) Mudar o dono do diretório para root:
```
sudo chown root /tmp/dados
```

8) Mudar o grupo do diretório dados para root:
```
sudo chgrp root /tmp/dados
```

-
