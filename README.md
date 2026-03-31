# Roteiro de Viagem em JSON

Este projeto agora carrega todo o roteiro a partir do arquivo `roteiro.json`.

## Como executar

Como o navegador bloqueia `fetch` em `file://`, rode com servidor local:

```bash
cd /home/fabricio/projetos/viagens
python3 -m http.server 8000
```

Depois abra: `http://localhost:8000`

## Onde editar o roteiro

Edite apenas `roteiro.json` para alterar:

- dias, atividades, horarios e dicas
- barra de clima
- dados de hospedagem
- marca e datas exibidas no topo/rodape

## Estrutura principal do JSON

- `brand`, `heroDates`, `footer`
- `weather`: `fact`, `tip`, `minTemp`
- `lodge`: dados do card de hospedagem
- `days`: lista de dias com `items`
- `tips`: lista de dicas finais

Cada item de `days[].items` pode ser:

- atividade normal
- atividade com destaque: `variant: "highlight"`
- atividade noturna: `variant: "night"`
- separador de periodo: `{ "separator": "Noite" }`

## Mapa dos itens

O projeto exibe um mapa com marcador para todos os itens de atividade.

Para aparecer no mapa, cada atividade precisa de:

```json
"location": {
	"lat": -28.0156,
	"lng": -49.5924,
	"label": "Descricao do local"
}
```

Itens separadores (`separator`) nao usam localizacao.
