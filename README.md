## Eduardo Pereira

**Desenvolvedor full-stack · Brasília-DF**
Construí e mantenho o [Comanda Vexto](https://github.com/edx200/comandas-pro-portfolio) — software em produção, com cliente pagando.

---

### O que eu construí

**[Comanda Vexto](https://github.com/edx200/comandas-pro-portfolio)** — SaaS multi-tenant de gestão de comandas para restaurantes.

Fui garçom e anotava pedido em papel. Em fevereiro de 2026 comecei a escrever o sistema que eu queria ter tido. Hoje faço tudo sozinho, do código ao suporte ao cliente.

|  |  |
|---|---|
| **2 restaurantes** | em operação real e diária |
| **Desde 07/2026** | o primeiro cliente não parou um dia |
| **Android · Web (PWA) · Windows** | mesma base de código |
| **Play Store** | publicado |

**Stack:** Flutter/Dart · Firebase (Firestore, Auth, Cloud Functions em Node 22, Hosting, Storage) · ESC/POS para impressão térmica · integração fiscal (NFC-e) e de pagamento

---

### Segurança não foi item de checklist

Decisões que tomei no sistema, e o motivo de cada uma:

- **Isolamento multi-tenant nas regras do Firestore** — toda coleção operacional passa por `restaurantes/{rid}/`, e uma regra catch-all nega o que não foi declarado. Um restaurante não alcança o dado do outro nem forjando a consulta.
- **PIN nunca é validado no cliente** — o app sequer consegue ler a coleção de PINs. Uma Cloud Function compara o hash SHA-256, aplica rate limit (5 tentativas → 15 min de bloqueio) e grava auditoria. Tudo no servidor.
- **Chaves de API fiscal e de pagamento não saem do backend** — o app chama o callable; o provedor nunca é tocado pelo dispositivo.
- **Dinheiro é `int` em centavos, nunca `double`** — erro de arredondamento em caixa é dinheiro que some do bolso do dono.

---

### Para onde estou indo

Migrando de desenvolvimento para **Application Security / Cloud Security** — pelo caminho inverso do usual: já escrevi, publiquei e mantenho em produção o tipo de código que precisa ser defendido.

Estudando agora: PortSwigger Web Security Academy · threat modeling do meu próprio sistema · segurança em aplicações mobile.

---

### Formação

**Faculdade de Tecnologia e Inovação Senac-DF** — 4º semestre.
Projetos acadêmicos organizados por disciplina, cada um com o processo documentado no README.

---

🌐 [vextosoft.com.br](https://vextosoft.com.br) · 💼 [LinkedIn](https://www.linkedin.com/in/eduardo-pereira-415412370)
