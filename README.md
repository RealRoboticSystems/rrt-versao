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

```json
{
  "versao":   "1.4-beta",
  "tag":      "v1.4-beta",
  "nome":     "título do release",
  "url":      "link para o release (só acessível a quem tem acesso ao repositório privado)",
  "publicado":"2026-08-20T08:38:59Z"
}
```

Só o campo `versao` é obrigatório; os restantes enriquecem o aviso mostrado ao utilizador.

## Como se atualiza

Automaticamente, pelo workflow `publicar-versao.yml` do repositório das ferramentas, sempre que lá
é publicado um release. Também se pode editar este ficheiro à mão.