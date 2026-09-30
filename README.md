# TrainHub — MVP SaaS de Treinamento Corporativo

MVP funcional em Django para evoluir para um SaaS B2B de LMS/treinamentos corporativos.

## O que já funciona

- Login/logout
- Multiempresa por associação de usuário à organização
- Papéis: administrador, RH/gestor, instrutor e funcionário
- Cadastro de departamentos
- Cadastro de funcionários
- Cadastro de cursos
- Módulos e aulas
- Matrícula de funcionários em cursos
- Controle de progresso
- Certificado com código de validação
- Django Admin
- Banco SQLite por padrão e PostgreSQL via `DATABASE_URL`

## Como rodar no Windows

```powershell
py -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
copy .env.example .env
py manage.py migrate
py manage.py seed_demo
py manage.py runserver
```

Abra `http://127.0.0.1:8000/`.

### Contas de demonstração

Admin:
- e-mail/usuário: `admin@trainhub.local`
- senha: `Admin123!`

Funcionário:
- e-mail/usuário: `joao@trainhub.local`
- senha: `Aluno123!`

## PostgreSQL

Defina no `.env`:

```env
DATABASE_URL=postgresql://trainhub:senha@localhost:5432/trainhub
```

## Próximos módulos recomendados

1. Editor visual de cursos
2. Avaliações completas e banco de questões
3. Trilhas de aprendizagem
4. Relatórios e exportação CSV/XLSX/PDF
5. Notificações por e-mail
6. Assinaturas e billing (Stripe/Asaas/Mercado Pago)
7. Storage S3
8. MFA e auditoria avançada
9. API pública
10. IA para geração de cursos e questões

## Aviso de produção

Este repositório é um MVP. Antes de produção comercial, revise segurança, isolamento multi-tenant, LGPD, backups, observabilidade, armazenamento de arquivos e fluxo de cobrança.

## Rodando com Docker

```bash
docker compose up --build
```

Em outro terminal:

```bash
docker compose exec web python manage.py seed_demo
```

Depois acesse `http://127.0.0.1:8000/`.
