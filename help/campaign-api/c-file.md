---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 5%
---
# Arquivo (Classe)

Classe de arquivo

> Aviso:
>
> O acesso por meio de APIs de arquivo é limitado a **var**, **sftp** e pastas temporárias do Adobe Campaign.

Este é um exemplo de como usar a classe para ler e processar todas as linhas de um arquivo em sequência.

```javascript
var file = new File("/tmp/test.txt")
file.open()
for each(var line in file)
  logInfo(line)
file.close()
 
```

## Métodos

| Método | Descrição |
| --- | --- |
| [Arquivo](m-file-file.md) | Cria um novo objeto associado a um arquivo. |
| [fechar](m-file-close.md) | Fecha o arquivo. |
| [copiar para](m-file-copyto.md) | Copia um arquivo. |
| [descartar](m-file-dispose.md) | Libera os recursos usados pelo objeto. |
| [liberar](m-file-flush.md) | Força a gravação no disco |
| [lista](m-file-list.md) | Lista o conteúdo de um diretório. |
| [mkdir](m-file-mkdir.md) | Cria um diretório com o caminho do objeto [File](c-file.md) atual. |
| [abrir](m-file-open.md) | Abre o arquivo no modo de leitura ou gravação. |
| [remover](m-file-remove.md) | Exclui o arquivo. |
| [renomearPara](m-file-renameto.md) | Renomeia um arquivo. |
| [readln](m-file-readln.md) | Lê uma linha do arquivo de texto. |
| [rmdir](m-file-rmdir.md) | Exclui o diretório (não em cascata). |
| [wrieln](m-file-writeln.md) | Grava uma linha de texto no arquivo. |

## Propriedades

| Propriedade | Descrição |
| --- | --- |
| [canRead](p-file-canread.md) | Retorna verdadeiro se o arquivo puder ser lido. |
| [canWrite](p-file-canwrite.md) | Retorna verdadeiro se o arquivo puder ser modificado. |
| [existe](p-file-exists.md) | Retorna verdadeiro se houver um arquivo ou pasta com este nome. |
| [fullName](p-file-fullname.md) | Retorna o nome do arquivo em absoluto. |
| [isDirectory](p-file-isdirectory.md) | Retorna verdadeiro se o arquivo for um diretório. |
| [isFile](p-file-isfile.md) | Retorna verdadeiro se o arquivo existir e for um arquivo. |
| [isOpen](p-file-isopen.md) | Retorna verdadeiro se o arquivo estiver aberto. |
| [últimaModificação](p-file-lastmodified.md) | Retorna a última data de modificação no formato de um objeto Date. |
| [nome](p-file-name.md) | Retorna o nome do arquivo com a extensão, mas sem o caminho. |
| [caminho](p-file-path.md) | Retorna o caminho completo do arquivo finalizado pelo separador. |
| [tamanho](p-file-size.md) | Retorna o tamanho do arquivo em bytes. |

## Recursos

**Disponível em:**

* Gerenciamento de conteúdo
* Propriedades de entrega
* Regra de tipologia
* JSSP
* Método SOAP
* WebApp
* Fluxo de trabalho
