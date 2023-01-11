**[Google Cloud Platform (GCP)](https://www.treinaweb.com.br/blog/categoria/google-cloud-platform-gcp)**

# Criando instâncias de VM no Google Cloud Platform

Conheça o compute engine e veja como criar novas instâncias de VM no Google Cloud Platform.

 há 4 anos 6 meses

[Artigos](https://www.treinaweb.com.br/blog)Criando instâncias de VM no Google Cloud Platform

Conforme falado no post anterior [introdução ao Google Cloud](https://www.treinaweb.com.br/blog/conheca-o-google-cloud-platform/), a plataforma possui uma série de serviços para as mais diversas aplicações. Entre esses serviços os mais usados e conhecidos, são: Compute Engine e [App Engine](https://www.treinaweb.com.br/blog/o-que-e-o-app-engine-e-como-publicar-uma-aplicacao-nele/).

O Compute Engine é um produto no qual o Google Cloud vende poder de processamento, armazenamento e tráfego de rede em forma de serviço. Esse modelo de serviço é chamado de [IaaS (Infrastructure as a Service)](https://www.treinaweb.com.br/blog/caracteristicas-que-um-servico-precisa-ter-pra-ser-considerado-cloud-computing#niveis-servicos) onde a empresa de nuvem vende a infraestrutura do datacenter como serviço. A principal característica dele é que toda a parte de configuração do ambiente, segurança e atualização fica a cargo do cliente.

O recurso central do compute engine são as instâncias de VM ou também conhecidas como VPS (Virtual Private Server). Basicamente são máquinas privadas criadas dentro da estrutura do Google Cloud para ser usado como servidor. O poder de processamento, memória e armazenamento são escolhidos no momento da criação da máquina, assim como o sistema operacional que será instalado.



![Google Cloud - Compute Engine Básico](https://d2knvm16wkt3ia.cloudfront.net/assets/svg-icon/google-cloud-compute-engine.svg)

##### CursoGoogle Cloud - Compute Engine Básico

[Conhecer o curso](https://www.treinaweb.com.br/curso/google-cloud-compute-engine-basico)



## Criando a primeira VM

Vamos usar o Google Cloud Console para criar a primeira instância de VM. Uma vez logado na plataforma, selecione o projeto no qual a instância será criada, em seguida menu **Produtos e Serviços > Compute Engine > Instâncias de VMs**:

![Menu compute engine](https://dkrn4sk0rn31v.cloudfront.net/2018/05/09165349/menu-compute-engine.png)

Nessa página temos a lista de todas as instâncias criadas para esse projeto. Use o Botão **Criar Instância** para abrir a tela de criação:

![Tela de criação de Vms](https://dkrn4sk0rn31v.cloudfront.net/2018/05/09165409/criacao-novas-instancias-de-vm.png)

## Configurando a instância

Nessa tela definimos todas as configurações da instância. Vamos falar de cada uma em detalhes:

#### Nome

Identificação da instância no projeto.

#### Zona

É o datacenter onde a máquina ficará hospedada. Note que ao lado da Zona ele mostra o valor estimado mensal da instância:

![Estimativa de preço do compute engine](https://dkrn4sk0rn31v.cloudfront.net/2018/05/09165432/estimativa-de-preco-compute-engine.png)

O valor da instância varia conforme a zona escolhida devido aos custos locais, impostos e outros detalhes. As zonas localizadas em São Paulo são southamerica-east[1, 2 e 3], ao selecioná-la, observe que o valor estimado será alterado, infelizmente SP é uma das regiões mais caras e não só no Google Cloud Platform, na AWS também.

#### Tipo da máquina

Temos a opção de escolher máquinas com configurações pré-definidas pela plataforma, basta clicarmos na caixa de seleção, conforme abaixo:

![Escolha de recursos da instancia](https://dkrn4sk0rn31v.cloudfront.net/2018/05/09165501/recursos-de-hardware-da-instancia.png)

Caso nenhuma dessas configurações esteja de acordo com o que você precisa, você pode clicar em personalizar e alterar manualmente os recursos da máquina:

![Tela de personalização de recursos da instancia](https://dkrn4sk0rn31v.cloudfront.net/2018/05/09165515/recursos-de-hardware-personalizados-da-instancia.png)

Vale lembrar que quanto mais recursos selecionar mais caro ficará o custo da máquina. Sempre que alterar algo, você pode acompanhar o preço estimado ao lado da Zona escolhida. Vamos escolher a máquina padrão **n1-standard-1**.



![Google Cloud - App Engine](https://d2knvm16wkt3ia.cloudfront.net/assets/svg-icon/google-cloud-app-engine.svg)

##### CursoGoogle Cloud - App Engine

[Conhecer o curso](https://www.treinaweb.com.br/curso/google-cloud-app-engine)



#### Disco de inicialização

O disco de inicialização é o armazenamento que a instância utiliza para instalar o sistema operacional e seus arquivos. Ao clicar em alterar podemos escolher o tamanho do disco e o sistema que será instalado:

![Configurações de Disco e SO](https://dkrn4sk0rn31v.cloudfront.net/2018/05/09165542/configuracoes-de-disco-e-sistema-operacional-e1525896058950.png)

Alguns serviços de computação em nuvem como a Digital Ocean não permitem instalar sistemas operacionais proprietário como Windows Server nas instâncias. No caso da Google Cloud Platform podemos instalar esses sistemas de forma muito simples sem se preocupar com licença e nenhum outro detalhe. Selecione o Windows Server 2016 com tamanho do disco de 50GB.

Configuramos os aspectos mais importantes para o funcionamento básico da máquina, clique em **Criar** para finalizar o processo.

## Usuário e senha da máquina

A primeira coisa que precisamos fazer para conectar na máquina é definir usuário e senha para acesso. Na lista de máquinas clique na setinha do item conectar e selecione **Configurar a senha do Windows**:

![Lista de instâncias](https://dkrn4sk0rn31v.cloudfront.net/2018/05/09165630/lista-de-instancias-acesso-remoto.png)

Configure o usuário e será gerada uma senha automaticamente pela plataforma. Guarde esses dados.

## Conectando à máquina

Ainda na coluna conectar ao clicar na seta de opções podemos fazer o download do arquivo que contém os dados de conexão da máquina válidos para qualquer cliente RDP. Outra opção é acessar pelo próprio navegador clicando no botão RDP ao lado da seta que usamos anteriormente.

É necessário uma extensão para o Google Chrome, depois de instalada a extensão, ele perguntará o usuário e senha. Se tudo ocorrer corretamente terá o acesso a máquina com sucesso

![Acesso a máquina windows](https://dkrn4sk0rn31v.cloudfront.net/2018/05/09165700/maquina-windows-google-cloud.png)

Para instalar uma máquina Linux o processo é muito parecido, só vai mudar o cliente de acesso a ela, ao invés de RDP, terá de usar um cliente SSH.

## Finalizando

O Google Compute Engine possui uma série de facilidades e ferramentas que permitem o gerenciamento de forma muito profissional de estrutura em nuvem. É possível criar diversos discos para uma mesma máquina, instalar sistemas operacionais pré-configurados com Google Launcher e muito outros detalhes. Não deixe de acompanhar o blog e nossos lançamentos de cursos, em breve teremos muito mais novidades sobre compute engine e vários outros serviços do Google Cloud Platform.



- [#compute engine](https://www.treinaweb.com.br/blog/tag/compute-engine)
-  

- [#vps](https://www.treinaweb.com.br/blog/tag/vps)
-  

- [#instancia de VM](https://www.treinaweb.com.br/blog/tag/instancia-de-vm)

#### Autor(a) do artigo

![Elton Fonseca](https://secure.gravatar.com/avatar/2cee05645357ced0841ce76ba5569c72?s=241&d=mm&r=g)

##### Elton Fonseca

Professor e desenvolvedor. Formado em análise e desenvolvimento de sistema, pós graduado em engenharia e arquitetura de software. É autor de cursos em diversos temas, como, desenvolvimento back-end, cloud computing e CMSs. Nas horas vagas adora estudar sobre o mercado financeiro, cozinhar e brincar com pequeno Daniel. [@eltonfonsecadev](https://twitter.com/eltonfonsecadev)

[Todos os artigos](https://www.treinaweb.com.br/blog/autor/elton-fonseca)

#### Artigos **relacionados** [Ver todos](https://www.treinaweb.com.br/blog/posts)

- 

  

  ##### [Serviços gratuitos do Google Cloud Platform](https://www.treinaweb.com.br/blog/servicos-gratuitos-do-google-cloud-platform)

  Conheça os principais serviços gratuitos do Google Cloud Platform e seus limites de uso.

- 

  

  ##### [Conheça o Google Cloud Platform](https://www.treinaweb.com.br/blog/conheca-o-google-cloud-platform)

  O Google Cloud Platform é o serviço de computação em nuvem do Google. Ele possui uma quantidade enor...

- 

  

  ##### [O que é o App Engine e como publicar uma aplicação nele](https://www.treinaweb.com.br/blog/o-que-e-o-app-engine-e-como-publicar-uma-aplicacao-nele)

  Descubra o que é o App Engine, sua história e como fazer a publicação (deploy) de sua primeira aplic...

- 

  

  ##### [Configurando um servidor web para produção com o ServerPilot](https://www.treinaweb.com.br/blog/configurando-um-servidor-web-para-producao-com-o-serverpilot)

  Aprenda a configurar um servidor web com PHP e MySQL de forma rápida e segura, com gerenciador web d...

- 

  

  ##### [Carreira em Cloud Computing: o que estudar?](https://www.treinaweb.com.br/blog/carreira-em-cloud-computing-o-que-estudar)

  Confira neste artigo algumas dicas do que estudar para se tornar um bom profissional de Cloud Comput...

- 

  

  ##### [Você sabe a diferença entre um engenheiro e um arquiteto de software?](https://www.treinaweb.com.br/blog/voce-sabe-a-diferenca-entre-um-engenheiro-e-um-arquiteto-de-software)

  Confira neste artigo as diferenças de alguns cargos da área de TI.

- 

  

  ##### [Por que eu devo estudar Cloud Computing?](https://www.treinaweb.com.br/blog/por-que-eu-devo-estudar-cloud-computing)

  Confira neste artigo alguns motivos que nos mostram o porquê de valer a pena aventurar-se nessa área...

- 

  

  ##### [Node.js: por que você deve conhecer essa tecnologia?](https://www.treinaweb.com.br/blog/node-js-por-que-voce-deve-conhecer-essa-tecnologia)

  Neste artigo, Bruna Goss, da Umbler, esclarece o que vem a ser o Node.js, onde a sua utilização pode...

- 

  

  ##### [Java, C# ou PHP: qual linguagem escolher?](https://www.treinaweb.com.br/blog/java-csharp-ou-php-qual-linguagem-escolher)

  Qual linguagem escolher? Java, C# ou PHP? Quais são as vantagens de cada uma? Vamos analisar estas d...

- 

  

  ##### [Aumente a segurança na Digital Ocean com o Cloud Firewalls](https://www.treinaweb.com.br/blog/aumente-a-seguranca-na-digital-ocean-com-o-cloud-firewalls)

  Veja como é possível proteger os seus servidores na Digital Ocean usando o firewall nativo da plataf...

- 

  

  ##### [Criando uma máquina virtual com a VirtualBox](https://www.treinaweb.com.br/blog/criando-uma-maquina-virtual-com-a-virtualbox)

  Neste artigo veremos como criar uma máquina virtual utilizando a VirtualBox com o sistema operaciona...

- 

  

  ##### [No final das contas: o que é o Kubernetes?](https://www.treinaweb.com.br/blog/no-final-das-contas-o-que-e-o-kubernetes)

  Você sabe o que vem a ser o Kubernetes e como ele pode nos ajudar? Confira neste artigo.

###### ![TreinaWeb](https://www.treinaweb.com.br/assets/images/treinaweb-logo@2x.png)