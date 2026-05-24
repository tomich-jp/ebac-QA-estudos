# Módulo 3 — Conceitos fundamentais de QA

## QA x QC x Teste

QA: Quality assurance, refere-se a garantia de qualidade diretamente, a garantia de qualidade atua diretamente
nos processos e entradas, ou o foco é garantir que os processos sejam seguidos de forma padronizada inicialmente
garantindo assim a qualidade do software em produção.

QC: Quality control, são praticas de controle de qualidade após a produção do produto ou conclusão de sprint
visa principalmente garantir a qualidade do que foi desenvolvido e se seguiu a documentação e reuisitos inicialmente definidos
foca muito mais na solução pronta em si e no processo de garantir qualidade no que foi desenvolvido diretamente.

Teste: O teste é uma extensão da QC ou sejá é a forma que utilizamos operacional e pratica que utilizamos para 
garantir a qualidade do que foi desenvolvido e estruturado, ele usa como base as etapas de QA(documentação, padronização e requisitos)
e a de QC(etapa de produção) para testar tudo que foi desenvolvido assim garantindo que sejá funcional de qualidade e atinja as expectativas do cliente
que é o foco principal do QA.

## Verificação e Validação (V&V)

Verificação: Garante que o software está sendo construído corretamente,
ou seja, seguindo a documentação, os requisitos e os padrões definidos
pelo time. A pergunta central é: "Estamos construindo certo o produto?"
Acontece durante todo o processo de desenvolvimento.

Validação: Garante que o software atende à necessidade real do cliente,
ou seja, que o produto certo foi construído. A pergunta central é:
"Estamos construindo o produto certo?" Acontece principalmente após
o desenvolvimento, com testes e homologação.

Ponto importante: um software pode passar na verificação e reprovar
na validação. Isso acontece quando os requisitos foram mal levantados
— o sistema foi construído corretamente, mas não resolve o problema
do cliente.

## Shift Left

O conceito de shift left é o mais importante em QA pois, a qualidade deve ser implementada desda etapa mais inicial
no desenvolvimento de um software, seguindo essa pratica é possivel garantir que o software esteja sendo contruido da forma correta
e de acordo com oque foi solicitado pelo cliente, e ajuda na indentificação dos bugs e falhas o mais cedo possivel, 
pois um bug indentificado inicialmente na etapa de requisitos é muito mais barato para resolver do que quando encontrado em produção por exemplo.

## Bug x Defeito x Falha

Bug, defeito e falha se relacionam entre si, como um efeito domino, o defeito surge inicialmente com um erro de digitação no codigo
ou entendimento equivocado da documentação pelo dev, assim gerando um bug, que é ação inesperada do software um erro causado pelo defeito,
assim chegando na falha que é consequencia direta do bug o bug pode ser modular oiu de integração a falha atinge um sistema como um todo
é mais grave e pode ser mais dificil de resolver por que envolve mais partes do sistema em si
