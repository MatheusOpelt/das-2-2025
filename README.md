
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
