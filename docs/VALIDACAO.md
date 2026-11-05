# Validação da atividade

| Verificação | Resultado registrado |
| --- | --- |
| Origem dos comentários | O endpoint do professor respondeu HTTP 200 com um objeto contendo `id` e `comentario`. O cliente da aplicação também leu um comentário desse serviço. |
| Testes automatizados | 22 aprovados em Node.js 22. [Saída local](TESTES_LOCAIS.txt) e [execução no GitHub Actions](https://github.com/hqlcc/02-Azure-Cloud/actions/runs/41966021816). Em 05/11/2026, os mesmos 22 testes passaram em Node.js 24. |
| Infraestrutura Azure | Grupo de recursos, Storage Account, fila `sentimentos`, Azure AI Language F0, servidor SQL, banco `sentimentos` e Function App criados. [Histórico de comandos](COMANDOS_EXECUTADOS.md). |
| Publicação | A rota HTTPS da Function App respondeu sem autenticação em duas consultas externas. |
| Azure SQL | A HTTP Function consultou os totais de `dbo.Sentimentos`. Houve dois novos registros positivos entre as leituras. |
| Teste público | Em 05/11/2026, o total passou de 6 para 8 em 17 segundos. Ambas as respostas tinham HTTP 200 e as três chaves exigidas. [Resultado gravado pelo teste](evidencia-fluxo.json). |

O teste integrado pode ser executado após a publicação:

```bash
source .deploy/resources.env
npm run smoke -- "$TOTALS_URL"
```

Ele exige HTTP 200, as três categorias e aumento do total entre duas leituras. O arquivo `docs/evidencia-fluxo.json` guarda o resultado real quando o teste passa.
