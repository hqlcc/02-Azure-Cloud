# Entrega da AV-ICL-02

| Item | Link ou estado |
| --- | --- |
| Repositório público | [hqlcc/02-Azure-Cloud](https://github.com/hqlcc/02-Azure-Cloud) |
| Comandos executados para criar os recursos | [Registro de execução](COMANDOS_EXECUTADOS.md) |
| Endereço da HTTP Function | [GET /api/sentimentos/totais](https://func-icl02-02a82191.azurewebsites.net/api/sentimentos/totais) |
| Verificação pública em 05/11/2026 | HTTP 200 nas duas leituras. [Evidência em JSON](evidencia-fluxo.json). |

| Leitura | positive | neutral | negative | Total |
| --- | ---: | ---: | ---: | ---: |
| Inicial | 2 | 1 | 3 | 6 |
| Após 17 segundos | 4 | 1 | 3 | 8 |

A rota consulta a tabela do Azure SQL a cada requisição. Os valores acima registram o teste concluído às 04:38:56 UTC.
