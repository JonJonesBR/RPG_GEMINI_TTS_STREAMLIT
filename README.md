# ⚔️ RPG Textual com IA Gemini, Voz e Streamlit 🐉

# TESTE O GAME AQUI: https://9ec6-104-196-171-177.ngrok-free.app/

Bem-vindo ao RPG Textual com IA Gemini! Embarque em jornadas épicas moldadas por suas decisões e pela inteligência artificial avançada do Google Gemini. Este aplicativo web, construído com Streamlit, oferece uma experiência de RPG dinâmica e imersiva, com narração por voz opcional. Ele foi projetado para ser facilmente executado no Google Colab e acessado publicamente através do ngrok.

## ✨ Funcionalidades

* **Narrativa Gerada por IA:** Histórias e interações criadas em tempo real pelo modelo Gemini 1.5 Flash do Google.
* **Temas Variados:** Escolha entre diversos temas de RPG, como Medieval Clássico, Alta Fantasia, Futurista (Sci-Fi), Cyberpunk Noir, Steampunk, Velho Oeste, Pós-Apocalíptico e Investigação Sobrenatural.
* **Personalidades do Mestre (IA):** Defina o tom da sua aventura com diferentes estilos de mestre, incluindo Neutro, Épico, Sombrio, Engraçado e Misterioso.
* **Criação de Personagem:** Nomeie seu aventureiro, escolha uma classe pré-definida baseada no tema ou personalize a sua.
* **Duração da Aventura:** Selecione entre aventuras Curtas, Médias ou Longas, cada uma com um número aproximado de turnos.
* **Suporte a Voz (TTS):** Ouça as narrações do mestre com a integração do `edge-tts` (requer instalação e pode depender do navegador/SO).
* **Interface Web Interativa:** Jogue através de uma interface amigável construída com Streamlit.
* **Fácil Execução no Colab:** Configurado para rodar no ambiente do Google Colab com o mínimo de setup.
* **Acesso Público via Ngrok:** Compartilhe sua sessão de jogo com um link público gerado pelo ngrok.
* **Gerenciamento de Jogo:** Acompanhe o lore do mundo, história do personagem, localização atual, objetivo principal e inventário.

## ⚙️ Como Funciona

Este projeto combina várias tecnologias para criar a experiência de RPG:

* **Streamlit:** Utilizado para construir a interface gráfica do usuário (GUI) da aplicação web, permitindo a interação do jogador.
* **Google Gemini API:** O cérebro por trás da narrativa. O modelo de linguagem gera o enredo, as descrições, as respostas do mestre e os resultados das ações do jogador.
* **Edge-TTS:** Uma biblioteca Python que utiliza os serviços de Text-to-Speech da Microsoft Edge para converter as narrações do mestre em áudio.
* **Google Colab:** O ambiente de notebook baseado em nuvem onde o script Python é executado. Ele lida com a instalação de dependências e a execução do aplicativo Streamlit.
* **Ngrok:** Uma ferramenta que cria um túnel seguro da sua instância local do Colab (onde o Streamlit está rodando) para um URL público na internet. Isso permite que você acesse o aplicativo Streamlit de qualquer navegador.

## 📋 Pré-requisitos

* Uma **Conta Google** (para usar o Google Colab).
* Uma **Chave API do Google AI Studio (Gemini)**. Você pode obter uma em [Google AI Studio](https://aistudio.google.com/app/apikey).
* Uma **Conta Ngrok** e um **Authtoken do Ngrok**. Crie sua conta e obtenha seu token em [ngrok.com](https://dashboard.ngrok.com/get-started/your-authtoken).
* Um navegador da web moderno (Chrome, Firefox, Edge, etc.).

## 🚀 Configuração e Execução no Google Colab

Siga estes passos para rodar a aventura no Google Colab:

1.  **Obtenha suas Chaves:**
    * **Google AI Studio API Key:** Visite [Google AI Studio](https://aistudio.google.com/app/apikey) e crie/copie sua chave API.
    * **Ngrok Authtoken:** Acesse seu dashboard do [ngrok](https://dashboard.ngrok.com/get-started/your-authtoken) para copiar seu authtoken.

2.  **Abra o Script no Google Colab:**
    * Faça o upload do arquivo `.py` do projeto para o seu Google Drive e abra-o com o Colab.
    * Ou, se o projeto estiver no GitHub, você pode abri-lo diretamente no Colab usando o formato de URL: `https://colab.research.google.com/github/<SEU_USUARIO_GITHUB>/<NOME_DO_REPOSITORIO>/blob/main/<NOME_DO_ARQUIVO.py>`.

3.  **Configure os Secrets no Colab:**
    * No notebook Colab, clique no ícone de **chave (🔑)** na barra lateral esquerda ("Secrets").
    * Clique em "**ADICIONAR UM NOVO SECRET**".
    * Adicione o seguinte secret:
        * **Nome:** `NGROK_AUTHTOKEN`
        * **Valor:** Cole o seu Authtoken do ngrok aqui.
        * Marque a caixa de seleção "**Acesso ao notebook**".
    * Salve o secret.

4.  **Execute as Células do Notebook:**
    * O script fornecido normalmente tem três partes principais:
        1.  Uma célula para instalar as dependências (`pip install ...`).
        2.  Uma célula que escreve o código do aplicativo Streamlit para um arquivo (`%%writefile rpg_streamlit_app.py`).
        3.  Uma célula final que executa o aplicativo Streamlit e inicia o túnel ngrok.
    * Execute cada uma dessas células em ordem.

5.  **Acesse o Jogo:**
    * Após a execução bem-sucedida da última célula, você verá uma mensagem indicando que o túnel ngrok foi estabelecido, seguida por um URL público (ex: `https://<id_aleatorio>.ngrok.io`).
    * Copie este URL e cole-o na barra de endereços do seu navegador.
    * A interface do RPG Streamlit deve carregar.

## 🎮 Como Jogar

1.  **Configuração da API (na barra lateral):**
    * Na barra lateral do aplicativo Streamlit, insira sua **Chave API do Google AI Studio** no campo correspondente.
    * Clique no botão "**🔗 Configurar API**". Você deverá ver uma mensagem de sucesso.

2.  **Criação da Aventura (na barra lateral):**
    * **Nome do Aventureiro(a):** Digite o nome do seu personagem.
    * **Estilo do Mestre (IA):** Selecione a personalidade que a IA narradora terá.
    * **Escolha o Tema:** Selecione o cenário da sua aventura.
    * **Escolha sua Classe:** Escolha uma classe pré-definida que muda de acordo com o tema, ou digite uma classe personalizada no campo abaixo.
    * **Duração da Aventura:** Escolha quão longa você quer que sua aventura seja.
    * Clique no botão "**🚀 Iniciar Aventura!**".

3.  **Interaja com o Mestre:**
    * A IA irá gerar a introdução da sua aventura. Esta e as narrações subsequentes do mestre aparecerão na aba "**📜 Narrativa e Ações**".
    * Se o TTS estiver funcionando, você poderá ouvir a narração (um player de áudio aparecerá).
    * No final da aba "Narrativa e Ações", você encontrará um campo de chat com o texto "**O que você faz?**". Digite sua ação e pressione Enter.
    * A IA processará sua ação e responderá, continuando a história.
    * Mudanças no jogo (novo objetivo, localização, inventário) serão notificadas por toasts e adicionadas à narrativa.

4.  **Acompanhe sua Jornada:**
    * **Aba "📊 Status e Opções":** Veja um resumo do seu personagem, turno atual, objetivo, localização e inventário. Você também pode sair da aventura aqui.
    * **Aba "📖 Lore da Aventura":** Relembre o estilo do mestre, o lore do mundo, a história do seu personagem e seu objetivo principal.

5.  **Fim da Aventura:**
    * Quando o número máximo de turnos para a duração escolhida for atingido, a aventura será concluída.
    * Você pode então iniciar uma nova aventura.

## 🛠️ Solução de Problemas Comuns

* **`ERRO: Token NGROK_AUTHTOKEN não encontrado...`**:
    * Verifique se você adicionou o secret `NGROK_AUTHTOKEN` corretamente na seção "Secrets" (🔑) do Colab.
    * Certifique-se de que marcou a caixa "Acesso ao notebook" para o secret.
    * Confirme que o nome do secret é exatamente `NGROK_AUTHTOKEN` (maiúsculas).

* **`Erro crítico ao iniciar o túnel ngrok` ou Ngrok não conecta**:
    * **Authtoken Inválido:** Seu authtoken do ngrok pode estar incorreto, expirado ou mal configurado no Colab Secrets. Verifique-o no dashboard do ngrok.
    * **Limites da Conta Ngrok:** Contas gratuitas do ngrok têm limites de túneis simultâneos ou largura de banda. Certifique-se de que não há outros túneis ngrok ativos em sua conta se estiver atingindo limites. O script tenta fechar túneis antigos, mas pode falhar.
    * **Problemas de Rede no Colab:** Raramente, o Colab pode ter problemas de conectividade.
    * **Interferência:** Às vezes, processos ngrok anteriores podem interferir. O script tenta matar processos antigos, mas você pode precisar reiniciar o runtime do Colab (`Ambiente de execução > Reiniciar ambiente de execução`).

* **`Erro na API Gemini` ao configurar ou durante o jogo**:
    * **Chave API Inválida:** Verifique se a Chave API do Google AI Studio inserida na interface do Streamlit está correta e ativa.
    * **Cotas da API:** Você pode ter atingido os limites de uso da API Gemini. Verifique seu console do Google Cloud ou a documentação da API.
    * **Problemas de Serviço:** Pode haver uma interrupção temporária no serviço da API Gemini. Tente novamente mais tarde.

* **Voz (TTS) não funciona / Sem áudio**:
    * **Biblioteca `edge-tts`:** O script tenta instalar `edge-tts`. Verifique se não houve erros durante a instalação na primeira célula do Colab. Mensagens de aviso sobre `edge-tts` não encontrado serão exibidas se a importação falhar.
    * **Conectividade TTS:** O serviço `edge-tts` depende de conexão com servidores da Microsoft. Pode haver problemas temporários de rede ou serviço.
    * **Navegador/Bloqueadores:** Seu navegador ou alguma extensão (como bloqueadores de script/anúncio) pode estar impedindo a reprodução automática de áudio ou a funcionalidade do `edge-tts`.

* **Aplicativo Streamlit não carrega no link ngrok (ex: `Connection Refused`)**:
    * **Tempo de Inicialização:** O Streamlit pode levar alguns segundos para iniciar completamente após a execução da célula. Aguarde um pouco mais (o script já inclui um `time.sleep(10)` para isso, mas em alguns casos pode ser mais lento).
    * **Erros no Streamlit:** Verifique a saída da célula do Colab que inicia o Streamlit. Pode haver mensagens de erro do próprio Streamlit impedindo sua inicialização.
    * **Reiniciar:** Tente reiniciar o ambiente de execução do Colab (`Ambiente de execução > Reiniciar e executar tudo`) e tente novamente.

* **"nest_asyncio aplicado para Streamlit" ou "cannot apply nest_asyncio"**:
    * Esta é uma mensagem informativa ou um aviso relacionado à execução de código assíncrono (para o TTS) dentro do ambiente Streamlit. Geralmente, se o TTS funciona, você pode ignorá-la. Se o TTS falhar consistentemente, pode ser um ponto de investigação, mas o script tenta lidar com isso.

## Contribuições

Contribuições, sugestões e reports de bugs são bem-vindos! Sinta-se à vontade para abrir uma issue ou um pull request.

---
