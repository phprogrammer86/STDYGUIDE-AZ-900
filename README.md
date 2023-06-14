# STDYGUIDE-AZ-900

# Cerificação AZ900 - Fundamentals

## Conteúdo

*  Conceitos de cloud (20 - 25%)
* Principais serviços Azure (15 - 20%)
* Principais soluções e ferramentas de adm no Azure (10 - 15%)
* Recursos gerais de segurança e segurança de rede (10 - 15%)
* Descrever recursos de identidade, governança, privacidade e conformidade (20 - 25%)
* Descrever a adm de recursos do AZure e Service Level Agreements (10 - 15%)


## Conceitos e vantagens da nuvem

* Alta disponibilidade 
* Distribuição geográfica
* Escalabilidade
* Agilidade
* Plano de recuperação
* "Pay as you go" | Pague pelo que usar
  -> Custo de operação mais barato
  -> Roda sua infraestrutura de forma mais eficiente
  -> Escala quando seu negócio precisa de mudanças


## Modelos de serviços de nuvem

* IaaS (infraestrutura como serviço)
	-> A infraestrutura, ou, o hardware é mantido pelo provedor da nuvem, não sendo necessário, portanto, se preocupar com a infraestrutura física que será necessária para o negócio

* PaaS (Plataforma como serviço)
	-> Não é necessário se preocupar com o sistema operacional, ou seja, com a plataforma disponibilizada não será necessário instalar serviços de banco de dados por exemplo e etc, toda a plataforma já estará disponível

* SaaS (Serviço)
	-> Todo o serviço é disponibilizado em todos os níveis


## Serverless

* É a computação sem servidor, a própria plataforma (conceito de Paas) gerencia o hardware necessário para cada aplicação.

## Tipo de nuvem

* On Premises 
 -> Todo o serviço de nuvem é privado, da própria empresa
 * Hibrido
 -> O serviço é compartilhado, uma parte fica em uma nuvem pública(AZ, aws e etc) e outra parte na nuvem privada
 * Off Premises
 -> A empresa usa 100% o serviço de uma nuvem pública. 

## Infraestrutura global Azure

* A infraestrutura da Azure tem  dois componentes, físico e os componentes de conectividade de rede, os datacenters físicos são distribuídos em regiões pelo mundo, cada continente/país representa uma "geografia", as cidades são "regiões" e as regiões tem as suas "zonas"
* Zonas de disponibilidade
	-> Datacenters fisicamente separados dentro de uma região da Azure, por exemplo, a Azure tem na região de São Paulo datacenters separados em 3 zonas diferentes, essas zonas garantem a disponibilidade do serviço, cada região possui no mínimo 3 zonas disponíveis
* Cara região é sempre pareada com outras regiões na mesma geografia, para caso ocorra algum problema, como desastres naturais, uma região suprir a outra, elas devem estar a uma distancia minima de 300 milhas

## Azure marketplace

* Dentro do marketplace da Azure vários recursos como ISO de SOs, blockchains, banco de dados, estrutura de códigos, wordpress, tudo já fica disponível para ser usado pelo usuário do serviço

## Azure CLI

* Comandos AZ dentro do terminal, todos os comandos começam com az. Acesso todos os recursos do portal em linha de comando. - https://docs.microsoft.com/en-us/cli/azure/reference-index?view=azure-cli-latest
* Como é dentro de um terminal bash, podem ser usados recursos do linux como grep 

## Serviços de computação

### Azure virtual machines
  -> VM é uma emulação de software em computadores físicos, inclui processadores, memória, armazenamento e recursos de rede, tudo isso de forma virtual. Ela provê IaaS e essa infraestrutura pode ser usada de diferentes maneiras
  -> As VMs tem um recurso scale set que gera possibilidade de escalonar  as maquinas, criar e gerenciar grupos de VMs. O numero de VMs é automaticamente acrescentada ou retirada de acordo com a demanda do usuário
### Azure App services
  -> Serviço baseado em HTTP para hospedagem de web apps. Ele se enquadra em Paas, hospeda tanto web site quanto web app e o back-end da api.
### Azure container instances
* A instancia de container Azure é uma solução para qualquer cenário para operar conteiners isolados, sem orquestração. Para ambientes maiores e mais complexos é usada a tecnologia do Kubernets.

### Azure kubernetes service

* No kubernets (azure kubernets service - AKS) entra a questão da orquestração dos containers, os clusters serão gerenciados pela azure e o cliente fica responsável pelos nós, ou seja, as imagens (iso). A azure fica com as tarefas mais críticas, como monitoramento e manutenção do sistema. O serviço AKS é gratuito, o usuário só paga pelas maquinas que usar

### Windows virtual desktop

* Provê de forma rápida estações de trabalho com infraestrutura windows, windows 365 apps, multi-sessoes windows 10, windows 7 e serviçoes de desktop remotos (RDS) 

### Azure functions

* Solução serveless para manter um código com um minímo de infraestrutura garantida pela azure, esse codigo pode ser disparar de acordo com o que for setado apartir de um gatilho (trigger) e toda a infra para ter esse codigo na VM será garantido pela azure




## Redes

### Azure Virtual Network (Rede virtual)

* Vnet é a base para que possamos fazer nossa rede virtual dentro da Azure. Conceitos:
	-> Espaço de endereçamento (Address space), é a atribuição dos IPs dentro da rede.
	-> Subnets, são sub redes dentro da rede.
	-> Regions, redes idependentes por região.
	-> Subscription, dentro de uma assinatura podemos ter varias redes dentro dela

### Load Balancer

* Balanceamento de tráfego opera na camada 4 do modelo OSI, ele confere se os servidores estão funcionando e se sim vai distribuindo o tráfego entre as máquinas. Ele pode ser tanto interno quanto público. Ele suporta os protocolos HTTP/HTTPS e TCP/UDP e faz esse balancemanto através de IPs ou portas

### Application Gateway

* Opera dentro da camada 7, trabalha dentro do HTTP olhando cabeçalho, url e etc. Quando a requisição chega no app gateway, ele olha a regra e faz a entrega interna. Faz o balanceamento do tráfego através da url

### VPN Gateway

* Serve para interligar a nuvem da azure ao on-premises do cliente ou dentro da propria azure de forma segura
* ExpressRoute - conexão direta sem passar pela internet

### CND (Content Delivery Network)

* Coloca o conteúdo em cache para ser entregue de forma mais rápida. Também pode acelerar conteúdo dinâmica através de POPs (pontos de acesso)

## Storage

Links úteis:
	https://learn.microsoft.com/pt-br/azure/storage/common/storage-redundancy#zone-redundant-storage

### BLOB
	-> São arquivos (objetos), serve para otimizar o armazenamento de grandes dados não estruturados, imagem, arquivos de log, vídeos, texto e etc. Arquivos no geral que são guardados dentro de um container para que seja feito o armazenamento de cada um deles.

### DISK
	-> Condição que temos de acrescentar outro disco, podendo ampliar o storage, ou seja, a capacidade de armazenamento
https://learn.microsoft.com/pt-br/azure/virtual-machines/disks-types
https://docs.microsoft.com/pt-br/azure/virtual-machines/linux/attach-disk-portal

### FILE
	-> Serviço de file share, compartilhamento. Da suporte a protocolos SMB e NFS

### Archive
	-> Classe de armazenamento

### Acess tiers (níveis de acesso) - Storage

* Classificação dos dados do storage dentro dos 3 tipos abaixo

	Hot -> nível de armazenamento em que o acesso é mais frequente

	Cool -> acesso com não tanta frequência, arquivados por pelo menos 30 dias

	Archive -> acesso mais raro, para um backup e etc, arquivados por pelo menos 180 dias, mais barata, porem se acessar com muita frequência fica mais caro.

## DataBase

### Cosmos DB

	-> Banco de dados "no cicle" oferecido pela azure, totalmente gerenciado. é PaaS

### Azure SQL

	-> Sql vinculado a nuvem da azure, tem o serviço SQL database totalmente autogerenciado, o serviço SQL managed instances em que são criadas instancias mas tambem autogerenciadas e o serviço SQL VMs em que o usuário pode optar por gerenciar caso precise mexer em algo dentro do sistema operacional, é boa para migração assim como a anterior.

### MySQL

	-> Sql não vinculado a microsoft

### Postgree

	-> Está em três formatos na plataforma, servidor flexivel, unico ou hyperscala

### DataBase migration services

	-> A ideia básica é transportar os dados do on premises para a nuvem, é um assistente de migração. A ferramenta de migração de dados chama DMA
https://docs.microsoft.com/en-us/sql/dma/dma-overview?view=sql-server-ver15

## Azure Solutions

### IoT

	-> Ter um unico lugar para centralizar, gerenciar e monitorar os serviços da azure, Azure central, o IoT Hub vai gerenciar todos os dispositivos associados a nuvem
https://docs.microsoft.com/en-us/azure/iot-central/core/overview-iot-central

### Big Data

	-> Azure Data Lake Analytics, serviço de analise de dados da azure

### DevOps

	 -> Azure Boards, fazer gestão do projeto
	 -> Azure Pipelines
	 -> Azure Repos
	 -> Azure Test Plans, criar planos de teste
	 -> Azure Artifacts, criar artefatos 

https://azure.microsoft.com/en-us/services/devops/
## Segurança

### Defense in Depth

	-> Defesa em profundidade (camada), usa multiplos perímetros de defesa até a proteção do dado que é a sua finalidade. Sempre baseado nos conceitos de Integridade, Confidencialidade e Disponibilidade

https://learn.microsoft.com/en-us/training/modules/secure-network-connectivity-azure/2-what-is-defense-in-depth



### Security Azure Firewall

	-> Serviço de segurança de rede baseado em nuvem, similar ao firewall de rede. Tem alta disponibilidade interna, em zonas, escalabilidade e etc.

 [https://docs.microsoft.com/pt-br/azure/firewall/features](https://docs.microsoft.com/pt-br/azure/firewall/features)
 
 [https://docs.microsoft.com/pt-br/azure/architecture/example-scenario/firewalls/](https://docs.microsoft.com/pt-br/azure/architecture/example-scenario/firewalls/)

### Network Security Groups (NSG)

	-> Pode-se entender o nsg como se fosse um firewall interno, é complementar ao firewall, faz a filtragem na camada de rede, limitando o trafego e o acesso aos recursos internos

### Azure DDoS Protection

	-> Camada de proteção dentro da nuvem da azure para mitigar ataques de negação de serviço. Esta dubdividida entre os planos basic e standard

https://docs.microsoft.com/pt-br/azure/ddos-protection/ddos-protection-overview

### Azure Defender

	-> Provê alertas de segurança e e proteção avançada contra ameaças para VMs, bancos de dados sql, containers, webapp, a rede e mais

https://docs.microsoft.com/pt-br/azure/security-center/azure-defender

### Azure Security Center

	-> Dashboard que mapeia o ambiente de segurança, fazendo acompanhamento, mapeamento e gerando relatórios. Tem proteção hybrida, tanto na azure quanto on premises
 
### Azure Key Vault

	-> Como se fosse um cofre digital que guarda as informações de segurança

### Azure Information Protection (AIP)

	-> Serviço de classificação das informações, para atender normas, questões regulatórias e etc. É uma solução baseada em nuvem que permite que as organizações descubram, classifiquem e protejam documentos e emails aplicando rótulos ao conteúdo. 	
	O AIP faz parte da solução Microsoft Information Protection (MIP) e estende a funcionalidade de rotulagem e classificação fornecida pelo Microsoft 365.

### Azure Threat Protection

	-> Proteção contra ameaças integrada ao AD, monitora logs de acesso

### Azure Sentinel

	-> Ferramenta de Siem da azure, monitora os eventos e gera os alertas

### Azure Dedicated Hosts

	-> Maquinas dedicadas dentro da azure, maquinas fisicas individuais para esses clientes


## Identity Services / Compliance

### Azure Active Directory (AAD)

	-> Gerencia de identidade de usuarios dentro da nuvem e on premises

https://docs.microsoft.com/pt-br/azure/active-directory/fundamentals/active-directory-compare-azure-ad-to-ad

### Single Sign-On

	-> Um usuário é válido para autenticar em outros serviços

https://docs.microsoft.com/pt-br/azure/active-directory/manage-apps/sso-options

### Multi-Factor Authentication

	-> Pode ser habilitado o multi fator de autenticação para maior proteção dos usuarios.

### Azure Policy

	-> Criação de politicas para os serviços e o que cada uma afeta, tem painel informativo para controlar as politicas

### Azure RBAC

	-> Controla as regras de acesso aos recursos, é um sistema de autorização criado pela azure resource manager

### Azure Monitor

	-> Centralizar em real time tudo que esta acontecendo na VMs, analise de logs, operaçes de suporte, coletar dados e etc. Na criação da VM marcar 'Enable OS guest diagnostics'. Pode coletar dados de máquinas virtuais e aplicativos em outras nuvens e locais.

### Azure Health

	-> O Azure oferece um conjunto de experiências para manter o cliente informado sobre a integridade dos seus recursos de nuvem. Essas informações incluem problemas atuais e futuros, como eventos de impacto de serviço, manutenção planejada e outras alterações que podem afetar sua disponibilidade. O usuario tambem pode criar um alerta

### Compliance

* https://docs.microsoft.com/en-us/azure/compliance/
    
* https://servicetrust.microsoft.com/
