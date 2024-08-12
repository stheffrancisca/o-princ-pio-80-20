# o-princ-pio-80-20
Usando o princípio 80/20 para analisar uma empresa de bebidas

### Um dos princípios mais importantes nas empresas é o princípio 80/20. No geral, 20% das ações que uma empresa faz geram 80% dos resultados. Isso tanto para receita, quanto para custos, etc. Você está analisando uma empresa de bebidas. Tendo isso em mente, queremos descobrir quais as linhas de custos que representam 80% do total gasto da empresa. Para isso, calcule quanto percentualmente cada custo representa do custo total da empresa e crie um ranking decrescente baseado nesse percentual 

custos = [
    (10131.7, "Custo Mercadorias Vendidas"),
    (2916, "Logística"),
    (1741, "Despesas Comerciais"),
    (1305, "Despesas administrativas"),
    (28, "Outros Itens"),
    (997, "Juros e Resultado Financeiro"),
    (14, "Participações em outros Empreendimentos"),
    (58, "Impostos")
]

custos.sort(reverse=True)
total = sum(item[0] for item in custos)

percentual_acumulado = 0
for i in range(len(custos)):
    valor, descricao = custos[i]
    percentual_acumulado += (valor / total)
    custos[i] = (valor, descricao, valor / total, percentual_acumulado)

print(custos)
