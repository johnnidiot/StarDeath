# StarDeath — protótipo de portfólio

## Abrir
Extraia o ZIP e abra `index.html` em um navegador moderno. Para melhor compatibilidade, sirva a pasta por um servidor estático local.

## O que funciona nesta versão
- Layout responsivo roxo/preto, estrelas, constelações e detalhes animados.
- Galeria inicial com as artes fornecidas.
- Filtros públicos: todas as artes, artes feitas para a Fandub LuxDub Studios, comissões/pedidos externos e projetos pessoais.
- Área administrativa com senha local, cadastro de imagens, edição de título/descrição/categoria e exclusão.
- Botão **Salvar alterações** ao editar uma obra e **Salvar arte** ao criar uma nova.
- Filtro de categoria também dentro do painel administrativo.
- Armazenamento no IndexedDB deste navegador e exportação/importação de backup JSON.

## Como separar as artes
Ao adicionar ou editar uma obra, escolha **Onde esta arte deve aparecer?**:
- **Artes feitas para a Fandub LuxDub Studios** — todos os trabalhos da LuxDub, incluindo os de anime.
- **Comissões & pedidos especiais** — pedidos externos, como *Black Numbers* e a arte de Halloween.
- **Meu universo criativo** — trabalhos pessoais.

A escolha fica salva junto da obra e determina em qual filtro ela aparece na galeria.

## Limitação importante de segurança e armazenamento
Esta é uma versão estática de demonstração. A senha é verificada no navegador e as obras ficam guardadas apenas no dispositivo/navegador em que foram adicionadas. Isso não é segurança suficiente para um site publicado: alguém com conhecimentos técnicos pode contornar a barreira local, e as alterações não sincronizam automaticamente entre dispositivos.

Para restringir de verdade o painel só à Maggie em um site público e sincronizar imagens entre celular e computador, a próxima etapa é integrar autenticação real e armazenamento no servidor (por exemplo, Supabase ou Firebase) com regras de acesso administrativas. Não use esta versão como se já tivesse autenticação de produção.

## Novidades: redes sociais, créditos e apoio
- Botão **Compartilhar** usa o menu de compartilhamento do dispositivo quando disponível; caso contrário, copia o link.
- Seção **Redes & créditos** para exibir os links sociais da Maggie e os links das pessoas/equipes que encomendaram cada arte.
- Ao editar uma obra, é possível preencher **Pessoa/equipe que pediu** e **Link social da pessoa/equipe** (por exemplo, a conta da LuxDub).
- Seção **Apoie o StarDeath** com chave Pix e nome de recebedor configuráveis no painel. O visitante pode copiar a chave Pix.
- Na área **Personalizar o portfólio**, informe Instagram, TikTok, outra rede, chave Pix e nome de recebedor; depois clique em **Salvar redes e apoio**.

Essas configurações continuam locais neste protótipo. O botão de compartilhamento gera um link utilizável publicamente apenas depois que o site estiver hospedado. A chave Pix só aparecerá na página quando você a preencher no painel.


## Melhorias desta edição
- Campo de busca na galeria por título, descrição, categoria e nome de cliente, combinado com os filtros existentes.
- Contador mostra quantas obras correspondem à busca/filtro.
- Tecla `Esc` fecha o painel ou a visualização ampliada da imagem.
- Destaque visual de foco para navegação por teclado.
- Exportação de backup passa a incluir também obras padrão que foram editadas.

## Publicar online — importante
O projeto pode ser publicado como site estático, por exemplo com GitHub Pages, Netlify ou Cloudflare Pages. Para uma primeira publicação simples, envie o conteúdo da pasta `stardeath_portfolio` para um repositório GitHub e ative **Settings → Pages** escolhendo a branch e a pasta raiz. A URL pública só será criada pelo serviço depois de configurar a hospedagem.

**Limitação que permanece:** esta edição não cria um servidor, não configura um banco de dados online e não transforma a senha local em autenticação real. IndexedDB e as configurações ficam no navegador/dispositivo atual; a senha local não protege o painel contra alguém com conhecimento técnico. Não publique dados privados nem use a versão atual para administrar um portfólio público como se tivesse segurança de produção.

### Próxima etapa recomendada para a versão pública
1. Criar um projeto no Supabase ou Firebase.
2. Configurar autenticação real para que somente a conta administrativa autorizada acesse o painel.
3. Guardar imagens em armazenamento remoto e metadados em banco de dados com regras de acesso.
4. Testar as regras de segurança antes de publicar; nunca colocar chaves secretas de servidor no HTML.
5. Fazer backup das obras existentes antes de migrar. A exportação JSON atual é um backup local, não sincroniza os dispositivos automaticamente.

As fontes, cores, imagens existentes e a estrutura visual original foram preservadas; as melhorias são incrementais.
