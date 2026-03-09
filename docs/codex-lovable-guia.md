# Como usar o Codex para corrigir e melhorar um projeto no Lovable

## Fluxo recomendado (rápido e prático)

1. **Defina objetivo e escopo em uma frase.**
   - Ex.: “Corrigir bug no formulário de login e melhorar feedback de erro sem mudar o design geral.”
2. **Dê contexto técnico mínimo ao Codex.**
   - Stack (React/Vite, Supabase, etc.), arquivo/tela afetada e comportamento esperado.
3. **Peça diagnóstico antes da alteração.**
   - “Liste hipóteses da causa raiz e proponha plano curto antes de editar.”
4. **Peça mudança pequena por vez.**
   - Uma correção por commit/PR facilita revisar, testar e desfazer.
5. **Sempre peça validação.**
   - Testes, build, lint e checklist manual com passos reproduzíveis.
6. **Use loop de melhoria contínua.**
   - Ajuste prompt com o resultado anterior até chegar no padrão desejado.

## Prompt-base para usar com Codex

```text
Você é meu par técnico. Quero melhorar meu projeto no Lovable.

Contexto:
- Stack: <stack>
- Problema atual: <problema>
- Arquivos mais prováveis: <arquivos>
- Resultado esperado: <resultado>
- Restrições: não quebrar <x>, manter estilo <y>, mudar o mínimo possível.

Tarefas:
1) Diagnostique causa raiz com hipóteses priorizadas.
2) Proponha plano curto de implementação.
3) Aplique a menor mudança segura possível.
4) Mostre diff resumido e por que cada mudança foi feita.
5) Rode/indique testes e checklist manual.
6) Liste riscos e próximos passos.
```

## Casos comuns no Lovable

- **Bug visual/componente quebrado**
  - Informe tela, estado esperado e screenshots de antes/depois.
- **Integração/API falhando**
  - Passe payload de exemplo, status code, erro no console e ambiente afetado.
- **Performance ruim**
  - Peça medição (LCP/TTI), principais gargalos e otimizações com maior impacto primeiro.
- **Refatoração sem regressão**
  - Solicite extração incremental (sem “big bang”), com testes e commits pequenos.

## Boas práticas para obter respostas melhores

- Dê **inputs concretos** (erro exato, rota, arquivo, log).
- Peça **critérios de aceite** objetivos (“considero pronto quando…”).
- Exija **mudança mínima viável** antes de soluções grandes.
- Solicite **explicação para não especialistas** quando for entregar ao time.
- Mantenha histórico: “o que tentamos / o que funcionou / o que não funcionou”.

## Checklist antes de publicar

- [ ] Build e lint sem erros
- [ ] Fluxo crítico testado manualmente
- [ ] Sem regressão visual óbvia
- [ ] Mensagens de erro amigáveis ao usuário
- [ ] Log técnico suficiente para depuração
- [ ] PR com contexto, impacto, riscos e plano de rollback

## Exemplo de pedido objetivo

> “No projeto do Lovable, o botão ‘Salvar perfil’ não persiste telefone. Analise `ProfileForm` e integração com backend. Quero correção mínima com validação de campo, tratamento de erro amigável e testes do fluxo de sucesso/erro. Não altere layout.”

