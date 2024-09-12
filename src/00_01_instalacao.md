# Instalação

> A versão corrente de OCaml durante a escrita deste tutorial e que será usada como referência é a 5.2.0.

## Instale o OPAM

OCaml possui um gerenciador de dependências oficial, assim como JavaScript tem o npm, quando trabalhamos com OCaml
utilizamos o **O**Caml **Pa**ckage **M**anager (OPAM) que nos permite baixar e instalar ferramentas, bibliotecas e
gerenciar diferentes versões de OCaml.

Gerenciar diferentes versões de OCaml é uma vantagem que é importante. Existem pacotes do compilador de OCaml em
praticamente todos os gerenciadores de dependências Linux, mas instalar diretamente as ferramentas e compilador
é menos versátil e normalmente o pacote de OCaml disponível nos repositórios não é a última versão.

Segue abaixo as instruções conferme seu Sistema Operacional.

### 🐧 Linux

1. **Instale o gerenciador de pacotes**:

Se você está instalando no Debian ou Ubuntu:
```term
sudo apt update && sudo apt-get install --no-install-recommends -y opam
```
> A opção **--no-install-recommends** serve para dizer para o apt não instalar as dependências recomendadas, que nesse
  caso incluem o compilador OCaml que não queremos porque vamos instalá-lo depois.

Se você está usando uma distribuição baseada em Arch:
```term
sudo pacman -Syyu opam
```
> Observe que em ambos os casos estamos usando superusuário, **sudo**. É recomendável instalar o OPAM como root.

2. **Instale o compilador via o gerenciador de pacotes**:

A primeira coisa a fazer após instalar o OPAM pe usar o comando **init** para inicializá-lo. Como usuário não privilegiado
utilize o commando:
```term
opam init -y
```
Feche e abra seu terminal ou então rode o comando `eval $(opam env --switch=default)` para ativar o OPAM no novo ambiente.

Quando rodar o comando `opam` deve aparecer:
```
usage: opam [--version]
            [--help]
            <command> [<args>]

The most commonly used opam commands are:
    init         Initialize opam state, or set init options.
    list         Display the list of available packages.
    show         Display information about specific packages.
    install      Install a list of packages.
    remove       Remove a list of packages.
    update       Update the list of available packages.
    upgrade      Upgrade the installed package to latest version.
    config       Display configuration options for packages.
    repository   Manage opam repositories.
    switch       Manage multiple installation prefixes.
    pin          Pin a given package to a specific version or source.
    admin        Tools for repository administrators

See 'opam help <command>' for more information on a specific command.
```

3. **Instale as ferramentas para OCaml**:

Agora vamos instalar os pacotes necessários para trabalharmos com OCaml através do OPAM:

```term
opam install ocaml-lsp-server odoc ocamlformat utop
```

Isso deve ter instalado o compilador OCaml e as ferramentas necessárias, incluindo Dune que vai ser o project builder
que vamos usar.

### 🍎 MacOS

TODO

### 🪟 Windows

TODO
