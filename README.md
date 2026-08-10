# ALLOW-LIST-FIREWALLS

Nesta lista liberamos redes conhecidas a conectarem via SSL — redes que **NUNCA**
devem ser bloqueadas (infra Verkom + RFC1918), gerada automaticamente pelo
auto-block e sincronizada com este repositório a cada ciclo de 10 minutos.

## Arquivos

| Arquivo | Conteúdo | Formato |
|---|---|---|
| `allowlist.txt` | Redes liberadas (infra + RFC1918) | 1 CIDR por linha |
| `feed.json` | Metadata (gerado em, fonte, contagem) | JSON |

## Formato

- 1 item por linha, linhas com `#` são comentários
- `allowlist.txt`: CIDR (`177.104.0.0/16`)
- Atualizado automaticamente a cada ciclo do auto-block (10 min) quando há mudança

## Fontes

- **Allow:** whitelist hardcoded do `lib/block_sources.py` (RFC1918 +
  `177.104.0.0/16` WANs Verkom) + whitelist dos configs

## Consumo

Consumidores externos (firewalls, SOAR, scripts) podem ler o `allowlist.txt` via
raw URL do GitHub e comparar com o hash do `feed.json`.

**Repo irmão (block):** [verkombr/BLOCK-LIST-FIREWALLS](https://github.com/verkombr/BLOCK-LIST-FIREWALLS)

> 🌐 Repositório PÚBLICO — contém apenas faixas de rede conhecidas (sem dados sensíveis).
