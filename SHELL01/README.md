# SHELL01 - Descrição dos Exercícios

## Exercício 012

### Código:
```bash
id -G --name $FT_USER | tr " " "," | tr -d "\n"
```
Este comando utiliza o comando id para obter os grupos do usuário $FT_USER, depois utiliza tr para substituir espaços por vírgulas e tr -d "\n" para remover a quebra de linha. O resultado são os grupos do usuário separados por vírgulas.

## Exercício 02
### Código:
```bash
find . -type f -name "*.sh" -exec basename {} .sh \;
```
Aqui, find é utilizado para buscar arquivos (-type f) com extensão .sh na árvore de diretórios. O comando basename é utilizado para extrair os nomes dos arquivos sem a extensão .sh.

## Exercício 03
### Código:
```bash
find . -type f -o -type d | wc -l
```
Esse comando utiliza find para listar todos os arquivos e diretórios, e wc -l conta o número total de linhas, que corresponde ao número total de arquivos e diretórios.

## Exercício 04
### Código:
```bash
ifconfig | grep "ether" | cut -d " " -f10
```
O comando ifconfig exibe informações sobre interfaces de rede, e grep "ether" filtra apenas as linhas que contêm o endereço MAC. cut -d " " -f10 divide a linha em palavras e extrai o décimo elemento.

Exercício 05
Código:
Este exercício ainda não está disponível.

## Exercício 06
### Código:
```bash
ls -l | awk 'NR % 2 == 1'
```
O comando ls -l lista os arquivos em formato longo, e awk 'NR % 2 == 1' filtra as linhas ímpares, exibindo assim os arquivos de forma intercalada.

## Exercício 07
### Código:
```bash
cat /etc/passwd \
| sed '/^#/d' \
| awk 'NR % 2 == 0 {print $0}' \
| awk -F ":" '{  print $1 }' \
| rev \
| sort -fnr \
| awk -v FT_LINE1="$FT_LINE1" -v FT_LINE2="$FT_LINE2"  'NR >= FT_LINE1 && NR <= FT_LINE2 { print $0 }' \
| tr '\n' ' '  \
| sed 's+ +, +g' \
| sed 's+, $+.+g' \
| tr -d '\n'
```
Este comando extrai nomes de usuário do arquivo /etc/passwd, remove linhas comentadas, filtra linhas pares, ordena de forma reversa, e exibe apenas as linhas entre FT_LINE1 e FT_LINE2.

## Exercício 08
### Código:
```bash
echo $FT_NBR1 + $FT_NBR2 \
  | tr "'"'\\"?!mrdoc' '0123401234' \
  | xargs -I{} echo 'ibase=5;obase=23;'{} \
  | bc \
  | tr '0123456789ABC' 'gtaio luSnemf'
```
Este comando realiza operações matemáticas complexas convertendo números e caracteres com base em substituições específicas.

