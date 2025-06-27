# Monitoramento
azure monitor- insights e features de monitoramento
aplicativo cloud native
insights de rede, conteiners e vms
coleta metricas, logs de atividade e logs de diagnostico
alertas e notificações com prazo critico
monitoramento de serviços do azure, aplicativos,assinaturas do azure e locatários do azure
integração com grafana, powerbi.log analytics
comaprtilha informações com outras tecnologia do azure

Diferneça entre métricas e logs
metricas -valores numéricos que descrevem ualgum aspecto de um sistema em um momento no tempo
eles são leves e podem dar suporte a cenários quase em tempo real

logs-contem diferentes tipos de dados armazenados em registros
informação
métrica são números e logs são informações
envia dados ao log analytics para pesquisa avançada
consultar ou gerenciar eventos noo powershell cli e api rest
transmitir informações par ao hub de eventos
aruqivamento de dados em uma conta de armazenamento
analisar dados com powerbiComo o Azure Monitor organiza dados de log para consultas? 
O Azure Monitor organiza os dados de registo em tabelas. Sua empresa tem um site e os usuários estão relatando erros de conectividade e tempos limite. Você suspeita que uma regra de segurança possa estar bloqueando o tráfego de ou para uma das máquinas virtuais. Você precisa solucionar o problema rapidamente, qual das seguintes opções é a alternativa correta? 
Use o recurso IP Flow Verify do Network Watcher. O que o recurso Service Health permite acompanhar? 
A saúde dos serviços da Microsoft e notificações de indisponibilidade. Sua organização possui um web farm muito grande com mais de 100 máquinas virtuais. Você gostaria de usar o Log Analytics para garantir que essas máquinas estejam respondendo às solicitações. Você planeja automatizar o processo, então cria uma consulta de pesquisa. Você inicia a consulta identificando a tabela de origem do Log Analytics. Qual tabela de origem você usa? 
Heartbeat Sua empresa tem um site e os usuários estão relatando erros de conectividade e tempos limite. Você suspeita que uma regra de segurança possa estar bloqueando o tráfego de ou para uma das máquinas virtuais. Você precisa solucionar o problema rapidamente, qual das seguintes opções é a alternativa correta? 
Use o recurso IP Flow Verify do Network Watcher. Você está interessado em encontrar uma ferramenta única para ajudar a identificar alta utilização da CPU da VM, falhas de resolução de DNS, regras de firewall que estão bloqueando o tráfego e rotas mal configuradas. Qual ferramenta você pode usar? 
Solução de problemas de conexão do Observador de Rede O que é o Observador de Rede do Azure?
É uma ferramenta do Azure que ajuda a monitorar, diagnosticar e analisar o tráfego de rede de recursos da infraestrutura como serviço (IaaS), como:
Máquinas virtuais (VMs),
Redes virtuais (VNets),
Gateways,
Balanceadores de carga.
❗ Não é voltado para monitorar recursos PaaS ou aplicações web.

🧰 Principais funcionalidades
🔎 1. Monitoramento
Ferramentas que ajudam a visualizar e acompanhar sua rede:
Topologia: mostra a estrutura da rede de forma gráfica e interativa.
Monitor de conexão: verifica o desempenho entre dois pontos (por exemplo, entre duas VMs).
🛠️ 2. Diagnóstico de rede
Ajuda a identificar e resolver problemas de rede com ferramentas como:
Verificação de fluxo de IP: checa se pacotes são permitidos ou bloqueados, e por qual regra.
Diagnóstico de NSG: analisa regras de segurança em VMs e gateways.
Próximo salto: mostra para onde o tráfego está sendo roteado.
Regras de segurança ativas: exibe todas as regras aplicadas a uma interface de rede.
Solução de problemas na conexão: testa uma conexão específica no momento.
Captura de pacotes: grava o tráfego de rede para análise detalhada.
Solução de problemas de VPN: ajuda a detectar falhas em conexões VPN.
📊 3. Tráfego
Ferramentas para registrar e visualizar o tráfego de rede:
Logs de fluxo: registram o tráfego IP nas redes (armazenados no Azure). ⚠️ Os logs de NSG (grupo de segurança) serão desativados em 30/09/2027. Use logs de rede virtual em vez disso.
Análise de tráfego: cria visualizações e relatórios a partir dos logs.

📈 Uso + Cotas
Mostra o uso atual e os limites de recursos de rede (como número de VMs, gateways etc.) em uma assinatura/região. Útil para planejar novas implantações.

📏 Limites principais
1 instância do Observador por região/assinatura.
100 monitores de conexão por região.
10.000 sessões de captura de pacotes por região.
1 operação de diagnóstico de VPN por vez.

🟢 Importante
É habilitado automaticamente ao criar ou atualizar uma VNet.
Sem custo adicional para a habilitação em si.
Se você recusou anteriormente, pode habilitar manualmente depois.

regras de alertas
para definir um alerta é necessário definir um escopo, escolher o sinal a ser monitorado, as condições a serem verificadas e os mecanismodes avaliação de alertas
exemplo: escopo:vm1 | sinal:uso da cpu |condições: média de uso da cpu 
mecanismo de avaliação de alertas:métricas e logs

é possível habilitar regras recomendadas tal como também é possível personalizar
grupos de ação- escolhe como ser notificado quando uma alerta for disparado
você pode adicionar até 5 grupos de ação para cada regras
é possível configurar sms, teams, email
Uma regra de alerta consiste em: 
Recurso, condição, ações, detalhes de alerta. 

para definir um alerta tem que primeiro selecionar o escopo, dispositivos ou grupo de dispositivos que sera monitora. condição, expressa os sinais verificados.ação, relativo ao grupos de açao e criação de alertas, ações disparadas se a condição for verdadeira. detalhes adição de descrições e definição de importanciasApós criar uma regra de alerta, o que é necessário para que ela seja ativada e enviada?
A ativação do monitoramento e a definição de condições e ações a serem executadas

log analytics
log analytics é um serviço que ajuda você a coletar e analisar dados gerados pelos recursos sem seus ambientes de nuvem e locais
escreve consultas de log e analisa interativamente seus resultados
por exemplo para avaliar atualizações do sistema e solucionar problema de incidentes operacionais
precisa antes criar um workspace para obter informações com base nos conectores que vão ir sendo configurados

workspace é um recuso do zure e é um conteiner no qual os dados são coletados, agregados analisados e apresentados
ambiente para fazer consultas, é possível criar mais de um e ambinetes especificos 
você pode ter vários workspaces por ssinatura do zure e ter acesso a mais de um workspace
um workspace fornece uma localização geografica, isolamento de dados e escopoanalise de logskql-linguagem de consulta para consultas comuns e personalizadas 
recuperar e consolidar rapidamente os dados no repositório
informações pode ser exportadas para powerbi ou excel
Para capturar o tráfego em uma VM, o Azure Network Watcher exige?
Extensão VM do Agente Observador de Rede

configurando monitor para a máquina
monitor>vm insigths>configurar insights da máquina
manda um agente de monitoramento para a máquina
depois criar uma regra de alerta> selecione o grupo de recuros> selecione a condição> adicionar grupo de ação e ações a serem feitas
voltar no resource group e testar
verificar o alerta no monitor

