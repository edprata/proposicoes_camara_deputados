# Classificação de Proposições da Câmara dos Deputados

Trabalho de nálise de Proposições da Câmara dos Deputados, com modelos de ML, para avaliar a probabilidade de aprovação de uma nova proposição. Este trabalho possui objetivo meramente didático, visando explorar e praticar técnicas de ML sem esgotar o tema e sem ter o compromisso de chegar a um modelo com alto grau de eficiência no seu resultado preditivo.


## Escopo

Projetos de leis e propostas de emendas à Constituição (PECs) são provavelmente os mais conhecidos produtos das atividades parlamentares. Mas também são proposições alguns outros tipos de documentos legislativos: pareceres sobre outras proposições, requerimentos, relatórios de CPIs, medidas provisórias do poder Executivo e emendas ao Orçamento da União, apenas para citar alguns.

Este trabalho se propõe a utilizar a base de proposições da Câmara dos Deputados para treinar um modelo de Classificação que possa prever se um projeto ainda não aprovado têm probabilidade de ser aprovado.

Para isso, trabalharemos apenas com os seguintes tipos de proposições da base:
- Projetos de leis;
- Emendas à constituição (PECs).

No final, pretende-se que, ao apresentar um projeto de lei ou emenda à constituição ainda não aprovado, o modelo diga se poderá obter aprovação.


## Conclusão

Foi necessário fazer um longo e moroso trabalho de exploração de dados e de pesquisa sobre os conceitos ligados ao tema, principalmente para o entendimento de quais estados indicam aprovação, quais indicam reprovação e quais indicam que a proposição ainda está em tramitação. A dificuldade na determinação desse critério levou à muitas idas e vindas, tornando o trabalho mais longo que o esperado e conduzindo à muitas conclusões parciais equivocadas - e consequente reavaliação constante de todo código.

Tentei realizar todo o trabalho com a biblioteca Pycaret, uma lib low code com uma proposta muito interessante. Porém, na parte de anlálise exploratória e tratamento de dados a lib deixa bastante a desejar. Logo, foi necessário incluir muitos outros recursos e até um código que eu já venho desenvolvendo há algum tempo para objetivo semelhante. Ainda assim, a lib Pycaret mostrou-se bastante útil, principalmente na comparação de modelos. Embora os critérios dessa comparação não estejam muito claros e evidentes, dá ótimos indícios de em quais modelos investir melhor. A Pycaret possui ainda recursos de otimização que, por falta de tempo, não cheguei a explorar.

Sobre os resultados da análise dos dados e dos modelos, pude confirmar a hipótese de que o autor e o partido político exercem uma forte influência sobre a aprovação ou não da proposição. Também foi possível encontrar, na análise de relevâncias das features, um viés claro relacionado ao evento mais importante do período analisado, que foi a Pandemia de COVID 16. Isso demonstra o quanto o trabalho de legislar é influenciado sobre questões sociais, a mídia e a opinião pública. Apesar de tantas alterações na legislatura, sabemos que o resultado do combate à pandemia foi desastroso e também sabemos que crises sanitárias não podem ser resolvidas por uma grande alterações nas leis vigentes do país, pois é uma questão médica e de saúde públic e não política.

Para finalizar, há muitas melhorias que gostaria de ter feito, porém não houve tempo hábil:
- Usar toda a massa de dados para fugir do viés causado por um evento restrito no tempo, que foi a Pandemia de COVID 19;
- Usar uma massa maior também poderia ajudar a tratar vieses relacionados a partidos políticos e de pessoas específicas da política, já que cargos mudam e eleições se ganha e se perde. Seria o caso de testar para saber se haveria eficácia nesta estratégia;
- Fazer uma análise de quais métricas seriam mais adequadas para avaliar os resultados, de acordo com a necessidade específica deste trabalho;
- Usar técnicas de tunning tanto da biblioteca Pycaret quanto outras para comparar os modelos e produzir resultados mais adequados;
- Fazer uma análise descritiva mais abrangente para tentar identificar outros vises que poderiam ser tratados. Analisei apenas as proposições aprovadas, mas gostaria de ter visto o restante do conjunto de dados;
- Testar algorítimos de regressão para estimar o percentual de probabilidade de aprovação ao invés de dizer apenas que uma proposição poderá ou não aprovada.
- Por último, tratar o desbalanceamento das classes.
