# SHELL01 - Descrição dos Exercícios

## Exercício 01

### Código:
```bash
id -G --name $FT_USER | tr " " "," | tr -d "\n"

### Explicação:
Este comando utiliza o comando id para obter os grupos do usuário $FT_USER, depois utiliza tr para substituir espaços por vírgulas e tr -d "\n" para remover a quebra de linha. O resultado são os grupos do usuário separados por vírgulas.