---
name: senatran_validar_cnh-mcp
description: Skill da REST API do SENATRAN: Validar CNH na MCP.AI: 1 endpoint em /api/senatran_validar_cnh. SENATRAN: Validar CNH, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# SENATRAN: Validar CNH — REST API skill

Você tem acesso à **SENATRAN: Validar CNH** REST API na MCP.AI.

> SENATRAN: Validar CNH, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/senatran_validar_cnh
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/senatran_validar_cnh/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"cpf":"...","registro":"...","codigo_seguranca":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/senatran_validar_cnh/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `senatran_validar_cnh_consultar`

SENATRAN: Validar CNH, consulta em fonte oficial. _(POST /api/senatran_validar_cnh/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf` | string | Sim | Parâmetro de consulta "cpf". |
| `registro` | string | Sim | Parâmetro de consulta "registro". |
| `codigo_seguranca` | string | Sim | Parâmetro de consulta "codigo_seguranca". |
| `nome_condutor` | string | Não | Parâmetro de consulta "nome_condutor". |
| `nome_mae` | string | Não | Parâmetro de consulta "nome_mae". |
| `login_cpf` | string | Não | Parâmetro de consulta "login_cpf". |
| `login_senha` | string | Não | Parâmetro de consulta "login_senha". |
| `pkcs12_cert` | string | Não | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Não | Parâmetro de consulta "pkcs12_pass". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_senatran_validar_cnh` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
