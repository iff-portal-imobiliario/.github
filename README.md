# .github
## 🏠 Projeto 18 — Portal Imobiliário (Listagem de Imóveis)

**Autor:** João Pedro

### 📌 Descrição
Portal web onde corretores de imóveis ou proprietários podem anunciar imóveis para aluguel ou venda. Clientes podem pesquisar, aplicar filtros e salvar seus imóveis favoritos.

### 👥 Perfis de Usuário
- **Corretor (Anunciante):** Pode gerenciar seus próprios anúncios.
- **Cliente (Interessado):** Pode pesquisar, filtrar e favoritar imóveis.
- **Administrador:** Gerencia o sistema e os usuários.

### ⚙️ Lógica de Negócio Principal
- O **Corretor** (usuário com `ROLE_CORRETOR`) pode **criar, editar e excluir** seus próprios anúncios.
- O **Cliente** pode **pesquisar e aplicar filtros** (preço, bairro, número de quartos) em todos os anúncios.
- O **Cliente** pode **salvar anúncios** em sua lista de favoritos (relação `ManyToMany` entre `Usuario` e `Anuncio`).
- O **Cliente** pode **enviar uma mensagem de interesse** sobre um anúncio. A API salva essa mensagem e a associa ao corretor dono do anúncio, que poderá visualizá-la em seu painel.

### ✅ Requisitos Funcionais (RFs)
- **RF-01:** O corretor pode gerenciar (CRUD) seus próprios anúncios, incluindo múltiplas fotos.
- **RF-02:** O cliente pode pesquisar e filtrar imóveis por preço, bairro e número de quartos.
- **RF-03:** O cliente pode salvar anúncios como favoritos (`ManyToMany`).
- **RF-04:** O cliente pode enviar mensagens de interesse visíveis ao corretor.

### 🚀 Requisitos Não Funcionais (RNFs)
- **RNF-01:** A busca (RF-02) deve ser otimizada com **Busca Full-Text** para filtros complexos. *(Desafio C7)*
- **RNF-02:** O upload de múltiplas fotos (RF-01) deve ser tratado com **processamento assíncrono** de thumbnails. *(Desafio C6)*
