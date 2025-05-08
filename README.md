
# Design e Arquitetura de Software II

## Configuração de usuário e e-mail no GitHub

```
git config --global user.name ""
git config --global user.email ""
```

## Aula – 27/02/2025

### Trade-offs
Resultado das decisões na escolha de ferramentas e tecnologias ideais para um projeto.

- **Durabilidade:** Informações persistentes, comuns em sistemas transacionais.
- **Cache:** Armazenamento temporário em memória que melhora a velocidade de acesso a dados.

### Escalabilidade
Capacidade de manter a performance da aplicação mesmo sob grande volume de requisições.

- **Servidor Local:** Gerenciamento fixo com maior controle.
- **Servidor em Nuvem:** Flexibilidade e segurança para crescer conforme a demanda.

### Automatização
Automatização de processos e operações de sistemas.

- Aplicações que monitoram servidores e disparam alertas.
- Sistemas que recriam instâncias automaticamente.
- Processos que restauram aplicações automaticamente.

### Infraestrutura como Código (IaC)
Infraestrutura definida através de código.

- Evita erros de configuração manual.
- Facilita a padronização de alterações.
- Aumenta a agilidade no deploy e manutenção.

### Recursos Descartáveis
Tratar componentes como elementos facilmente substituíveis.

- Substituição simples de recursos com falha.
- Atualização automática de componentes antigos.

## Aula 06/03/2025 – Decisões de Projeto (Design Tradeoffs)

- **Infraestrutura como código (IaC)**: Automatiza a criação e manutenção de recursos. Oferece controle e repetibilidade, mas pode aumentar os custos se não for bem gerenciado.
- **Acoplamento de componentes**: Quanto mais interdependentes os serviços, maior o risco de falhas em cadeia. Utilizar réplicas e balanceadores pode minimizar esse problema.
- **Banco de dados relacional vs. NoSQL**:
  - *Relacional*: Crescimento vertical, uso de réplicas apenas para leitura.
  - *NoSQL*: Crescimento horizontal, mais flexível e com suporte a múltiplas réplicas de escrita e leitura.
- **Redundância**: Ter sistemas prontos para substituir os principais em caso de falha.
- **Backup por log**: Permite replicar alterações sem copiar o banco inteiro.
- **Gerenciamento de custos**: Usar recursos apenas quando realmente necessários.
- **Uso de cache**: Reduz carga em bancos principais e acelera acessos frequentes.
- **Privilégios mínimos**: Conceder apenas as permissões essenciais a cada usuário.
- **Proximidade da infraestrutura**: Posicionar dados próximos dos usuários reduz a latência.
- **Zonas especiais de computação**:
  - *Local Zone*: Computação mais próxima dos usuários em locais específicos.
  - *Wavelength*: Baixa latência para aplicações móveis via 5G.

## Aula 10/03/2025 – Segurança em Nuvem e Distribuição de Conteúdo

- **Edge Locations**: Posição física para cache de conteúdo, melhora desempenho.
- **Cache regional**: Intermediário entre a origem e o edge.
- **Modelo de segurança compartilhada**: AWS cuida da infraestrutura; o cliente, das configurações e dos dados.
- **Autenticação e proteção de dados**: Reforçar autenticação e criptografar dados em trânsito e em repouso.
- **Segurança em camadas**: Proteger todas as partes da aplicação.
- **Controle de acesso ao banco de dados**: Evitar acessos diretos e permitir apenas via aplicação autenticada.
- **Auditoria e rastreamento**: Monitorar e registrar acessos e ações.
- **Resposta a incidentes**: Ter processos definidos e simulados.
- **Automatização de segurança**: Reduzir erro humano.
- **Princípio do menor privilégio**: Acesso apenas ao necessário.
- **Criptografia obrigatória**: Ativada por padrão.

## Aula 13/03/2025 – Gerenciamento de Acesso e Credenciais

- **Autenticação**: Validar identidade com algo que se sabe, tem ou é.
- **MFA**: Ativação obrigatória.
- **Rotação de chaves**: Evitar chaves permanentes e desatualizadas.
- **Armazenamento seguro**: Nunca expor credenciais em código.
- **Usuário root**:
  - Deve ser usado apenas quando necessário.
  - Ativar MFA imediatamente após criação.
- **Acesso programático**: Utilizar roles e permissões temporárias.
- **Acesso via console**: Geralmente com login de usuário e MFA.

## Aula 17/03/2025 – Controle de Acesso e Tipos de Armazenamento

- **RBAC**: Controle baseado em papéis.
- **Policies (Políticas)**:
  - *De identidade*: Aplicadas a usuários/grupos.
  - *De recurso*: Ligadas a serviços/objetos.
- **Políticas contêm**: Ações, recursos e efeitos (allow/deny).
- **Tipos de armazenamento**:
  - *Bloco*: EBS, usado por EC2.
  - *Arquivo*: FSx, EFS.
  - *Objeto*: S3.

## Aula 20/03/2025 – Armazenamento com S3

- **S3**: Alta durabilidade e disponibilidade.
- **Usos**: Backup, sites estáticos, análise de dados.
- **Storage Gateway**: Sincroniza sistemas locais com a nuvem.
- **Multipart Upload**: Upload em partes de arquivos grandes.
- **Direct Connect**: Conexão física com a AWS.
- **Transfer Family**: Compatibilidade com protocolos legados.
- **Classes de armazenamento**:
  - *Standard*: Acesso frequente.
  - *Standard-IA / One Zone-IA*: Acesso esporádico.
  - *Intelligent-Tiering*: Ajusta conforme uso.
  - *Glacier*: Arquivamento de longo prazo.
- **Outposts**: AWS em datacenter local.

## Aula 24/03/2025 – Gestão e Segurança no S3

- **Regras de ciclo de vida**: Automatizam movimentação/exclusão de objetos.
- **Versionamento**: Mantém histórico de alterações.
- **Exclusão com versionamento**: Cria marcador de exclusão (não apaga imediatamente).
- **CORS**: Controla acesso entre domínios.
- **Privacidade e criptografia por padrão**.

## Aula 03/04/2025 – EC2 e Tipos de Computação

- **EC2**: Serviço de máquinas virtuais com escalabilidade.
- **AMI**: Imagem de máquina usada para replicar instâncias.
- **EBS**: Armazenamento persistente vinculado à instância.
- **Níveis de gerenciamento**: De IaaS (EC2) a Serverless.
- **Compute Optimizer**: Sugestões de custo/desempenho.
- **Sistemas de arquivos**:
  - *FSx*: Windows.
  - *EFS*: Linux.

## Aula 07/04/2025 – Distribuição e Estratégias de Disponibilidade

- **Metadata Instance**: Obtenção de informações da instância.
- **HPC**: Computação de alto desempenho com baixa latência.
- **Spread**: Distribuição para alta disponibilidade.
- **Partition**: Alta disponibilidade com alguma afinidade.
- **Modelos EC2**:
  - Sob demanda, reservadas, spot, saving plans.
- **Segurança**: Evitar alterações manuais, automatizar configurações.

## Aula 10/04/2025 – Bancos de Dados na AWS

- **Critérios de escolha**: Tipo de dado, carga, custo.
- **Serviços**:
  - *RDS*: Gerenciado, relacional.
  - *Aurora*: Versão otimizada do RDS.
  - *DynamoDB*: NoSQL.
  - *ElastiCache, Neptune, Redshift*: Outros modelos especializados.
- **Aurora Serverless**: Autoescalável, cobra por uso.

## Aula 17/04/2025 – Segurança em Bancos e KMS

- **RDS Proxy**: Pool de conexões para reduzir sobrecarga.
- **Backups**:
  - *Automático*: Até 35 dias.
  - *Manual (snapshot)*: Indefinido.
- **KMS**: Serviço de gerenciamento de chaves.
  - *Simétrica*: Mesma chave para criptografar e descriptografar.
  - *Assimétrica*: Chaves diferentes.
- **DynamoDB**: Alta performance, criptografia automática.
- **Redshift**: Data warehouse para BI e análises históricas.
- **Outros bancos**: DocumentDB, Neptune, Timestream, Quantum Ledger.

## Aula 05/05/2025 – VPC e Sub-redes

- **VPC**: Rede virtual isolada dentro da AWS.
- **CIDR**: Define faixa de IPs da VPC.
- **Sub-rede pública**: Permite tráfego direto com a internet.
