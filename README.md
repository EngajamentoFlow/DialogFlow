<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2024/04/logo_github.png" width="240" />
<p align="center">Seja bem-vindo ao Guia de atualização do Dialogflow 🚀</p>
</p>
  
<p align="center"> 
<a href="https://hubconnect.top" target="_blank">👉 Participe da Comunidade HubConnect 👈</a>
</p>

<hr />
<hr />

## Configurando a integração do Dialogflow no Chatwoot

**Criar um novo Agente**


Acesse o Console do Dialogflow.

https://dialogflow.cloud.google.com

Usaremos o Dialogflow Essentials para este artigo. Clique em "Criar novo agente". Ele mostraria opções como mostrado abaixo.


<img src="https://www.chatwoot.com/docs/assets/images/create-new-agent-51f6b6bc6e6da84e81c18c0bbc06986a.png" alt="DialogFlow" width="1000" />

## Criar Interações


Você precisará criar intenções com base em como deseja que seu bot responda. 

Haverá 2 intenções padrão no projeto chamadas "Default Fallback Intent" e "Default Welcome Intent", conforme mostrado abaixo


<img src="https://www.chatwoot.com/docs/assets/images/default-intents-1159dded08111f981981ea9513cff68f.png" alt="DialogFlow" width="1000" />



## Agora que a configuração básica do bot está concluída, vamos criar uma conta de serviço e conectá-la ao Chatwoot


Você também pode criar intenções adicionais para seus casos de uso específicos.

O Chatwoot também oferece suporte a intenções avançadas que permitem transferência de agente , mensagens interativas , etc.

consulte: Intenções avançadas


## Criar uma CONTA


Para conectar este bot ao Chatwoot, você precisa criar uma conta de serviço em seu console do Google Cloud. 

Navegue até o console do projeto na nuvem do Google clicando no ID do projeto nas configurações do projeto abaixo.


<img src="https://www.chatwoot.com/docs/assets/images/project-settings-7e5fb3d738a18ead8c0298b7af2b8276.png" alt="DialoFlow" width="1000" />


Navegue até IAM e administrador -> Contas de serviço . Você verá uma visualização como a abaixo. Clique em "Criar conta de serviço".


<img src="https://www.chatwoot.com/docs/assets/images/service-account-console-418be807b0449cb5e3a1ba539a106407.png" alt="DialoFlow" width="1000" />

Forneça um nome de conta de serviço e uma descrição conforme mostrado abaixo.

<img src="https://www.chatwoot.com/docs/assets/images/service-account-details-4ab284d92f85ffca4f9f18702dcfc5b7.png" alt="DialoFlow" width="1000" />

Para fornecer acesso, selecione Dialogflow API Client no menu suspenso.

<img src="https://www.chatwoot.com/docs/assets/images/service-access-88029531f5f8437b409ed22d1e7cab8f.png" alt="DialoFlow" width="1000" />

Continue e clique em "Concluído". Agora, você poderá ver o serviço listado no painel. O próximo passo é criar uma chave para que ela possa ser compartilhada com o Chatwoot. Clique na conta de serviço e clique na guia "Chaves". Em seguida, clique em "Adicionar chave". Você será capaz de ver uma tela como a abaixo.

<img src="https://www.chatwoot.com/docs/assets/images/add-keys-885720919305b703fa3979807b445c7a.png" alt="DialoFlow" width="1000" />



## Clique em "JSON" e clique em "Criar". Ele geraria uma chave para sua conta de serviço, baixaria a chave e a salvaria para uso posterior.


O Chatwoot possui uma integração nativa do Dialogflow. 

Vá para "Configurações -> Aplicativos -> Dialogflow". 

Clique em "Configurar", você verá um botão para "Adicionar um novo gancho".

Você precisa adicionar "ID do projeto", "Arquivo de chave do projeto" e uma caixa de entrada para criar um gancho. 

(Copie o conteúdo do arquivo de chave baixado anteriormente e cole-o na área de texto)


<img src="https://www.chatwoot.com/docs/assets/images/add-to-chatwoot-463fe037a8269b447e13e5f9c3d4c891.png" alt="Quepasa-logo" width="1000" />


Voilá! A integração está completa.

Teste a caixa de entrada do site para ver se a consulta inicial é tratada pelo bot ou não


## Interações Avançadas


Criando uma 

Depois que o usuário solicita falar com o agente, o Dialogflow precisa informar ao Chatwoot que um agente agora pode assumir a conversa.

Crie uma intenção chamada "Intenção de transferência" com frases de treinamento como "Fale com um agente" ou "Fale com um agente" etc. Para lidar com a

intenção de transferência, criaremos uma resposta "Carga útil personalizada" conforme mostrado abaixo.


{
</p>
  "action": "handoff"
  </p>
}



<img src="https://www.chatwoot.com/docs/assets/images/handoff-intent-c24d32864b162046bd0ec929b0cc1be1.png" alt="Quepasa-logo" width="1000" />


Ao acionar uma intenção com a carga útil acima, o Chatwoot alternará o status da conversa para opene a entregará a um agente.


## Mensagens interativas


Nota: As mensagens interativas são suportadas apenas no canal do site no momento

A integração do chatwoot dialogflow também suporta mensagens interativas . Os seguintes tipos de mensagens interativas são suportados:

Opções : acompanhamento suportado

cartões

Artigos

Criando uma mensagem interativa 

Você pode criar outras mensagens interativas alterando a carga conforme mencionado na documentação de mensagens interativas.

Crie uma intenção com as frases de treinamento necessárias e uma resposta "Custom Payload" conforme mostrado abaixo para uma mensagem de opções.

Quando o usuário interage com as mensagens de entrada.

O valor selecionado é enviado de volta ao dialogflow, para que você configure uma intenção de acompanhamento, se necessário.

Exemplo : configurar um intent com a frase de treinamento "Gosto de biryani" para os casos em que o contato selecionar a opção "biryani".


Como um agente pode transferir a conversa de volta para o bot Dialoflow 

Quando o bot Dialoflow está conectado a uma caixa de entrada, as conversas são criadas com pendingstatus em vez de open. Isso permite que a triagem inicial

aconteça por meio do bot antes que a conversa seja passada para um agente. Quando handoffisso acontece, o status da conversa é alterado opene o bot para de

responder a ela.

Às vezes, os agentes gostariam de adiar uma conversa que foi transferida de volta para a fila do bot. Eles podem fazer isso alterando o status da conversa 

novamente pendingpara que o bot comece a responder a essa conversa novamente.

