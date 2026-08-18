# Relatório de Contexto — Site Pessoal cleitonmarinosantana.com.br

**Data:** 11/08/2026 · **Projeto:** Site pessoal profissional de Cleiton Marino Santana

## O que é o projeto

Site pessoal one-page criado a partir do Currículo Lattes de Cleiton (Superintendente de Desenvolvimento da CTI na SECITECI-MT, doutorando em Educação/UFMT, autor de 20+ livros de xadrez escolar). A identidade visual é **preto e branco, tema xadrez**, construída sobre a metáfora do próprio Cleiton: *a travessia do peão* (a2 → a8=♛), que representa sua carreira de professor de xadrez até superintendente. Fontes: Fraunces (display), Archivo (texto), IBM Plex Mono (notação). Tudo em arquivos HTML únicos com CSS/JS embutidos e fotos em base64.

## Estrutura do site (index.html)

Hero com tabuleiro 4×6 em que um retrato de Cleiton (foto DSC00844, P&B) aparece **em baixo relevo** sob casas semitransparentes (casas claras rgba(244,243,240,.84), escuras rgba(10,10,10,.78)); dama branca no a8 e peão no a3. Seções: Sobre (com foto sorridente DSC00030 e citação "A aprendizagem acontece no conteúdo; a transformação acontece na relação"), Números (20+ livros, 100+ trabalhos, 20 anos, 17 prêmios), Trajetória (timeline como lances de xadrez, casas a2→a8=♛, revelada com IntersectionObserver), Atuação (3 cartões), **Biblioteca**, banda fotográfica (DSC00968, peças flutuando), Prêmios, Formação, e rodapé com Contato + Recados.

### Biblioteca (seção #publicacoes)
Estado atual: **estante vazia de propósito** — Cleiton vai publicar os livros um a um. O catálogo completo de **28 obras está comentado dentro do JS** (const OBRAS), organizado em coleções: Educação na Era da IA (3: A Última Fronteira da Educação, A Nova Ciência da Aprendizagem, HACK School), HACK CLASS (5), Xadrez na Escola 1º–9º ano (9), Educação Infantil (2), Academia de Xadrez (7), Xadrez em MT (2). Para publicar um livro: remover o `// ` da linha dele e colar o link no campo `link:""` — o cartão de "estante sendo montada" some sozinho e os filtros aparecem. Capas são geradas em CSS (alternando preto/branco, peça de xadrez em marca d'água por coleção).

### Recados e Contato (rodapé)
Formulário "Deixe seu recado" (nome, cidade, mensagem) que abre o **WhatsApp (65) 99662-7072** com a mensagem pronta via wa.me, ou e-mail via mailto. Site é estático, sem banco — os recados não ficam salvos no site. Canais no rodapé: E-mail, Instagram, WhatsApp, Telefone, Lattes, LinkedIn, ORCID, Scholar, mais retrato em fundo escuro (DSC01002).

## Página /cursos (cursos.html)

Mesma identidade visual. **Curso 01 — Como Criar uma Associação** (programa "Gestão de Entidades — Curso Completo") com botão "Acessar o curso" apontando para **https://gestaodeentidades.com.br/** — a landing de vendas antiga, que era o que estava publicado no domínio cleitonmarinosantana.com.br antes (feita por outra pessoa, hospedada com DNS nsone.net) e continua no ar no endereço próprio. Cartões 02 e 03 como "Em preparação". Novos cursos entram um a um, como a biblioteca.

## Infraestrutura (feita nesta conversa, caminho B)

- **GitHub:** usuário `cleitonxadrez-stack`, repositório **`cleitonmarinosantana_`** (público), branch main, arquivos: `index.html`, `cursos.html`, `vercel.json` ({"cleanUrls": true, "trailingSlash": false}). Um PDF subiu por engano e foi excluído. Fluxo de atualização: substituir arquivo via "Add file → Upload files" (mesmo nome sobrescreve) → Commit → Vercel republica sozinho.
- **Vercel:** conta via login com GitHub (plano Hobby), projeto `cleitonmarinosantana`, deploy OK em `cleitonmarinosantana.vercel.app`. Domínios adicionados: `cleitonmarinosantana.com.br` (308 → www) e `www.cleitonmarinosantana.com.br`.
- **Registro.br:** nameservers **trocados com sucesso** de dns1–4.p08.nsone.net (backup dos valores antigos: dns1.p08.nsone.net, dns2.p08.nsone.net, dns3.p08.nsone.net, dns4.p08.nsone.net) para **ns1.vercel-dns.com / ns2.vercel-dns.com**. Houve aviso "Pesquisa recusada" na hora, mas salvou. No fim da conversa, aguardando propagação (Invalid Configuration no Vercel deve virar ✓ sozinho; não é preciso criar registros A/CNAME porque a delegação é por nameservers).

## Pendências

1. **E-mail:** o index.html publicado no GitHub ainda tem cleitonsantana@secitec.mt.gov.br; a versão corrigida (com **cleitonxadrez@gmail.com** no cartão de e-mail e no mailto dos recados) já foi gerada e entregue na conversa anterior — falta subir no GitHub.
2. **Instagram:** o site usa o palpite `@cleitonmarinosantana` — confirmar o @ real com Cleiton e corrigir se preciso.
3. **Confirmar propagação DNS** e o ✓ Valid Configuration no Vercel; testar cleitonmarinosantana.com.br e /cursos (aba anônima se houver cache).
4. **Publicar livros na biblioteca** um a um (descomentar em OBRAS + link) e **cursos futuros** (novos cartões em cursos.html).
5. Possível evolução futura já discutida: mural público de recados com Supabase; trocar capas geradas por capas reais dos livros; ordem definitiva da coleção "Educação na Era da IA" a confirmar (assumido: 1 Última Fronteira, 2 Nova Ciência, 3 HACK School).

## Dados de referência

Telefone/WhatsApp: (65) 99662-7072 · E-mail pessoal: cleitonxadrez@gmail.com · Lattes: lattes.cnpq.br/1382148648127357 · ORCID: 0000-0001-9999-0726 · LinkedIn: /in/cleiton-marino-santana-120575272 · Scholar: user=ZMZkXaAAAAAJ. Cleiton comunica em português informal, muitas vezes por ditado de voz; prefere passo a passo simples, sem jargão, com prints de tela como guia.
