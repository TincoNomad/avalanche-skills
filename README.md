# Avalanche skills

Agent skills for building on Avalanche. Two skills, one repo.

| Skill | Qué resuelve |
|---|---|
| [`x402-avalanche`](skills/x402-avalanche/SKILL.md) | pagos HTTP 402 con x402 sobre Avalanche: facilitator, headers `X-PAYMENT`, autorizaciones EIP-712 / EIP-3009, monetización por request para APIs y agentes de IA |
| [`eerc-avalanche`](skills/eerc-avalanche/SKILL.md) | tokens eERC (Encrypted ERC) privados en Avalanche: ERC-20 vs eERC, Standalone vs Converter, auditoría selectiva, zk-SNARKs, ElGamal, BabyJubJub, Poseidon |

Las dos están escritas para que un agente de código las use, no para leerlas de corrido.
Si eres humano, abre el `SKILL.md` que te interese.

## Instalar

Una skill:

```bash
npx skills add TincoNomad/avalanche-skills --skill x402-avalanche
npx skills add TincoNomad/avalanche-skills --skill eerc-avalanche
```

Sin `--skill`, el CLI te deja elegir cuál de las dos.

El comando detecta tu agente (Claude Code, Cursor, Windsurf, OpenCode) y escribe el archivo
que corresponda. Con pnpm es lo mismo: `pnpx skills add ...`.

## Estructura

```
skills/
  x402-avalanche/
    SKILL.md          frontmatter (name, description) + guía
    references/       detalle por tema, se cargan cuando la skill los pide
  eerc-avalanche/
    SKILL.md
    references/
```

Cada skill es autocontenida: su `SKILL.md` y sus `references/` se mueven juntos, y las rutas
internas son relativas al propio `SKILL.md`.

## Licencia

AGPL-3.0 — ver [LICENSE](LICENSE).
