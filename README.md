<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>FTP com Python</title>
</head>
<body>

<h1>FTP com Python</h1>

<p>
Este repositório contém um script Python que permite fazer upload de arquivos para um servidor FTP. O script é simples e fácil de usar, e pode ser adaptado para atender às suas necessidades específicas.
</p>

<h2>Requisitos</h2>

<ul>
  <li>Python 3.6 ou superior</li>
  <li>Biblioteca `ftplib`</li>
  <li>Biblioteca `vscode-api`</li>
</ul>

<h2>Como usar</h2>

<ol>
  <li>Clone o repositório para sua máquina.</li>
  <li>Instale as bibliotecas `ftplib` e `vscode-api` usando o gerenciador de pacotes Python `pip`:

```
pip install ftplib
pip install vscode-api
```

  </li>
  <li>Abra o arquivo `upload_ftp.py` em um editor de texto.</li>
  <li>Altere as configurações do servidor FTP conforme necessário.</li>

<pre>
config = {
    "host": "ftp.example.com",
    "port": 21,
    "username": "username",
    "password": "password",
}
</pre>

  </li>
  <li>Execute o script:

```
python upload_ftp.py
```

  </li>
</ol>

<h2>Exemplo</h2>

<p>
O seguinte exemplo irá fazer upload do arquivo `file.txt` para o servidor FTP no diretório atual:
</p>

```python
import ftplib
import vscode_api

# Configurações do servidor FTP
config = {
    "host": "ftp.example.com",
    "port": 21,
    "username": "username",
    "password": "password",
}

# Abre uma conexão com o servidor FTP
ftp = ftplib.FTP(config["host"], config["port"])

# Faz login no servidor FTP
ftp.login(config["username"], config["password"])

# Upload de um arquivo
ftp.storbinary("STOR file.txt", open("file.txt", "rb"))

# Fecha a conexão com o servidor FTP
ftp.quit()

# Registra um callback para o evento onSave
window.onSave(on_save)

def on_save(event):
    file = event.file
    print("O arquivo {} foi salvo.".format(file.name))

```

<p>
Este exemplo irá imprimir a mensagem "O arquivo file.txt foi salvo." sempre que um arquivo for salvo no Visual Studio Code.
</p>

<h2>Biblioteca vscode-api</h2>

<p>
A biblioteca `vscode-api` permite interagir com o Visual Studio Code através de uma API. Essa biblioteca fornece um método chamado `onSave()` que pode ser usado para registrar um callback que será chamado sempre que um arquivo for salvo.

Para usar a biblioteca `vscode-api`, você primeiro precisa instalá-la usando o gerenciador de pacotes Python `pip`:

```
pip install vscode-api
```

Depois de instalar a biblioteca, você pode importá-la no seu código:

```python
import vscode
```

Para registrar um callback para o evento `onSave()`, você pode usar o método `onSave()` do objeto `window`:

```python
def on_save(event):
    print("Um arquivo foi salvo!")

window.onSave(on_save)
```

<p>
Este código irá imprimir a mensagem "Um arquivo foi salvo!" sempre que um arquivo for salvo no Visual Studio Code.
</p>

</body>
</html>
