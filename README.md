
📌 Visão Geral do Projeto
Este projeto apresenta uma solução completa de Self-Service Business Intelligence desenvolvida na plataforma DIO. O desafio consistiu em extrair valor de uma base caótica de 100 registros de vendas da Porsche, utilizando um Agente de IA para o processo de ETL (Extract, Transform, Load) e estruturando um Dashboard Executivo de alta fidelidade diretamente no Microsoft Excel.

O grande diferencial desta entrega foi a transição de uma base de dados bruta para um produto de dados totalmente localizado, protegido e otimizado para o consumo da diretoria, eliminando poluição visual e blindando os gráficos contra erros de agregação.


🛠️ Arquitetura e Engenharia de Dados
O pipeline de dados foi desenhado para garantir tanto a governança quanto a usabilidade do usuário final, dividindo-se em:

Saneamento Lógico (Agente de IA): Padronização de datas para o formato ISO, conversão de milhas/quilômetros via RegEx e limpeza de strings financeiras (ex: convertendo multiplicadores como "k" para valores decimais puros).
Localização (PT-BR): Tradução integral dos cabeçalhos sanitizados para termos amigáveis de mercado (ex: ID da Venda, Data da Venda, Preço de Venda), facilitando a criação de relatórios autonômos.
Linhagem de Dados Protegida (Data Lineage): As colunas originais com os dados caóticos foram mantidas na planilha para fins de auditoria, mapeadas com o prefixo [BRUTO] e ocultadas, mantendo a tela limpa sem perder o histórico de transformação.

🛡️ Otimização para Dashboards e Tabelas Dinâmicas
Para garantir que a camada visual do Excel funcionasse perfeitamente, o tratamento de exceções foi refinado:

Remoção de Categorias de Erro: Todas as marcações de texto INVALID geradas na validação do schema foram limpas e substituídas por células vazias.
Blindagem de KPIs: Esta ação impede que o Excel crie barras ou fatias indesejadas rotuladas como "erro" ou "INVALID" nos gráficos dinâmicos, garantindo relatórios visuais limpos e somatórios matemáticos precisos.
Layout Corporativo: Planilha configurada com congelamento de painéis, formatação de moeda local, e Grid Lines ativas para navegação profissional.
