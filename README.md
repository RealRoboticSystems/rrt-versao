# rrt-versao

Um único ficheiro: [`versao.json`](versao.json) — a **versão publicada** das *Real Robotic Tools*
da [Real Robotic Systems](https://real-robotic-systems.pt).

## Para que serve

As **Real Robotic Tools** são um conjunto de ferramentas internas que abrem offline por
duplo-clique. O menu delas verifica, ao abrir, se a cópia que o programador tem é a mais recente —
e lê esse número **daqui**.

O repositório das ferramentas é privado, por isso a API do GitHub não responde a pedidos anónimos.
Em vez de obrigar cada pessoa a criar um *token*, publica-se apenas o número da versão neste
ficheiro. **Não há aqui código nenhum**, nem nada sobre projetos de clientes.

## Formato

Há **dois canais**: `estavel` e `beta`. Cada um leva a versão do conjunto e a de cada ferramenta
nessa release.

```json
{
  "estavel": {
    "versao": "1.3", "tag": "v1.3",
    "nome": "título do release",
    "url":  "link para o release (só acessível a quem tem acesso ao repositório privado)",
    "publicado": "2026-08-19T15:45:26Z",
    "ferramentas": { "linkador-io": "7", "editor-tabela-transicao": "1.12" }
  },
  "beta": { "…igual…" }
}
```

- `beta` é `null` quando a release mais recente já é a estável.
- Uma ferramenta que ainda não existia numa release não aparece nas `ferramentas` desse canal.
- Os mesmos campos aparecem também **no topo do ficheiro**, a apontar para a release mais
  recente: é o formato antigo, mantido para as cópias das ferramentas já distribuídas não
  partirem. Cópias novas leem os canais.

Do lado das ferramentas, a estável é que manda: quem está atrás dela é avisado; quem já está em
dia com ela apenas *fica a saber* que existe uma beta.

## Como se atualiza

Automaticamente, pelo workflow `publicar-versao.yml` do repositório das ferramentas, sempre que lá
é publicado um release. Também se pode editar este ficheiro à mão.