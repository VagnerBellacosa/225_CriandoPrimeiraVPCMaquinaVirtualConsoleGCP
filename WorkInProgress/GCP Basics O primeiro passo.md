# GCP Basics: O primeiro passo

### Conheça conceitos iniciais para dar um start no entendimento do uso da Google Cloud Platform.

Compartilhe este post: [![img](https://ilegra.com/wp-content/themes/ilegra-wp-theme/images/icons/linkedin.svg)](https://www.linkedin.com/shareArticle?mini=true&url=https://ilegra.com/blog/gcp-basics-o-primeiro-passo/&title=&summary=&source=) [![img](https://ilegra.com/wp-content/themes/ilegra-wp-theme/images/icons/facebook.svg)](https://www.facebook.com/sharer/sharer.php?u=https://ilegra.com/blog/gcp-basics-o-primeiro-passo/) [![img](https://ilegra.com/wp-content/themes/ilegra-wp-theme/images/icons/twitter.svg)](https://twitter.com/home?status=https://ilegra.com/blog/gcp-basics-o-primeiro-passo/) ![img](https://ilegra.com/wp-content/themes/ilegra-wp-theme/images/icons/copyLink.svg)

![img](https://ilegra.com/wp-content/uploads/2021/06/gcp-768x320.png)

A Google Cloud Platform (GCP) tornou-se uma das maiores concorrências da AWS, juntamente com a Azure da Microsoft, quando falamos em Cloud Computing. É de grande reconhecimento a quantidade de serviços oferecidos e a capacidade de integração dos mesmos. As ferramentas como o Google Drive e Google Fotos possuem armazenamento em nuvem e trazem uma ótima experiência para o usuário, imagine, então, os recursos disponibilizados pela GCP em um cenário corporativo. Os benefícios certamente estão presentes e auxiliam no crescimento de qualquer instituição que opte pelo uso da Cloud da Google. Basicamente, a GCP entrega uma plataforma segura, eficiente e promissora para empresas que buscam adotar o ambiente Cloud.

 

### Por onde começar?

Como qualquer ambiente Cloud, em um primeiro momento pode ser um pouco difícil e confuso interagir com a plataforma. Uma das vantagens da GCP é que ela apresenta um uso bem mais fácil ao ser comparada com a AWS, por exemplo. Outro benefício é a rica documentação que ela apresenta, portanto qualquer dúvida pode ser solucionada ao ler os conteúdos oficiais oferecidos pela Google. Para iniciantes, na própria documentação, há uma visão geral da plataforma que ensina diversos conceitos e explica de forma clara o funcionamento e princípios da GCP. [O link para esse conteúdo está aqui](https://cloud.google.com/docs/overview).

O primeiro passo para começar a se familiarizar com essa tecnologia é entender os serviços básicos que ela oferece. Como por exemplo, para computação e hospedagem, armazenamento, banco de dados e rede. A seguir, iremos ver os principais serviços básicos, demonstrando o serviço equivalente da AWS para uma melhor contextualização. A ideia central do presente artigo é demonstrar conceitos iniciais para dar um start no entendimento do uso da GCP, caso queira se aprofundar nos princípios apresentados, a documentação oficial é altamente recomendada para tal tarefa.

 

### VPC

A VPC (rede de nuvem privada virtual) da GCP equivale a VPC da AWS. Ou seja, serve para criação de redes virtuais definidas pelo usuário para utilização de recursos como instâncias (máquinas virtuais).

 

### Monitoring

É o serviço de monitoramento da GCP, equivalente ao CloudWatch da AWS. Com ele, é possível obter a visibilidade do uso e performance dos recursos da GCP, a partir da coleta de métricas.

 

### GCE

O GCE (google compute engine) é equivalente ao EC2 da AWS. Ou seja, é o serviço responsável por oferecer servidores virtuais hospedados na infraestrutura do Google, utilizando os recursos de escalonamento.

 

### GCS

O GCS (google cloud storage) é equivalente ao S3 da AWS. Ele permite o armazenamento de dados de qualquer tamanho, muito utilizado por empresas.

 

### Functions

É o serviço de funções da GCP, escalonável, que permite o gerenciamento de código sem o uso de servidores. Equivale ao Lambda da AWS.

 

### Colocando a mão na massa

![img](https://ilegra.com/wp-content/uploads/2021/05/imagem-2.gif)

Nada melhor do que explorar de forma prática as ferramentas para entender como elas funcionam, certo? Portanto, em seguida, iremos realizar as tarefas de criar uma GCE Free Tier, um bucket no GCS, fazer o upload de um arquivo nesse bucket, criar um arquivo na GCE e fazer sincronizações entre esses dois serviços. Dessa maneira, entenderemos melhor suas funcionalidades e o que pode ser feito a partir deles.

 

### Criando uma GCE Free Tier

Para criar uma GCE, ou seja, uma máquina virtual dentro da GCP é necessário seguir os próximos passos.

- Logar no console da GCP e no menu lateral, acessar o Compute Engine. Em instâncias de Vm, clicar em *Criar instância*.

![img](https://ilegra.com/wp-content/uploads/2021/06/IMAGEM-2.png)

Parte do menu superior na aba de Instâncias de VM

 

1. Em seguida, preencher o nome da instância.

2. Adicionar marcadores, neste momento é importante verificar a política de tags da empresa.

3. Selecionar a região, mantive a que estava por padrão.

   ![img](https://ilegra.com/wp-content/uploads/2021/06/IMAGEM-3.png)

4. Configurações da máquina, neste momento, também mantive a configuração por padrão.

5. Na seção de disco de inicialização é necessário selecionar o sistema operacional desejado. Nesse exemplo, utilizei o Linux Ubuntu 20.04.

6. E na seção de Identidade e acesso à API, marcar a opção de Permissão de acesso a todas APIs do Cloud.

7. Nas permissões de Firewall, permitir tráfego HTTP e HTTPS.

   ![img](https://ilegra.com/wp-content/uploads/2021/06/IMAGEM-4.png)

8. Ao fim da página, clicar em criar.

 

------

 

### Criando um bucket no GCS

Para criar um bucket no GCS é necessário seguir os próximos passos.

- No menu lateral, acessar o Cloud Storage.
- Na aba Navegador, clicar em Criar intervalo.

![img](https://ilegra.com/wp-content/uploads/2021/06/IMAGEM-5.png)

Parte do menu superior na aba Navegador

 

1. Agora, é preciso nomear seu bucket e continuar o processo.
   ![img](https://ilegra.com/wp-content/uploads/2021/06/IMAGEM-6.png)

2. Escolher onde armazenar seus dados, neste momento, eu deixei a opção Multi-region, que já estava selecionada por padrão.
   ![img](https://ilegra.com/wp-content/uploads/2021/06/IMAGEM-7.png)

3. Escolher uma classe de armazenamento padrão para os dados, neste momento, também mantive a opção padrão

    

   Standart

   .

   ![img](https://ilegra.com/wp-content/uploads/2021/06/IMAGEM-8.png)

4. Escolher como controlar o acesso aos dados, neste momento, optei pelo tipo detalhado.

   ![img](https://ilegra.com/wp-content/uploads/2021/06/IMAGEM-9.png)

5. Por fim, há as configurações avançadas que são opcionais. Mantive a que estavam por padrão.

6. Para finalizar, clique em criar no fim da página.

 

------

 

### Fazendo upload de um arquivo no bucket

Para realizarmos o upload de um arquivo no bucket recém-criado, é necessário seguir os seguintes passos.

- Acessar o *Cloud Storage* pelo menu lateral, na aba Navegador irá ter a lista de buckets criados. Clique no que você criou.

1. Criar pasta para armazenar os dados. Para isso, clique na opção Criar pasta no menu superior.

   

   ![img](https://ilegra.com/wp-content/uploads/2021/06/IMAGEM-10.png)

   Menu superior ao clicar no bucket criado.

2. Nomeie a pasta como desejar e após isso, acesse a pasta criada e clique na opção *fazer upload de arquivos*, no mesmo menu apresentado acima. Por fim, selecione o arquivo que deseja enviar para o bucket.

 

------

 

### Acessando instância GCE via SSH

Para executar tarefas dentro da instância criada, como criar arquivos, é preciso acessá-la primeiro. Para isso, a GCP oferece um terminal de conexão SSH atráves do navegador. Siga os próximos passos para realizar esse acesso.

- Acesse o menu lateral e clique em *Compute Engine*. Na lista de instâncias da VM, identifique a sua instância e na coluna *Conectar* selecione a opção *Abrir na janela do navegador*.

 

![img](https://ilegra.com/wp-content/uploads/2021/06/IMAGEM-11.png)

Opções ao clicar na coluna Conectar

 

------

 

### Criando arquivos dentro da instância GCE

Para criar arquivos, como um txt, dentro da instância criada é necessário seguir os seguintes passos.

- Primeiramente é necessário abrir o terminal de conexão via SSH como demonstrado no tópico anterior.

1. Digite o seguinte comando para criar uma pasta onde ficará armazenado o arquivo.
   *mkdir <nome da pasta>*
2. Entre na pasta criada, utilizando o comando abaixo.
   *cd <nome da pasta criada>*
3. Para criar o arquivoGCE.txt digite o seguinte comando.
   *touch arquivoGCE.txt*

 

------

 

### Sync entre o arquivo do bucket com a GCE

Para sincronizar o arquivo do bucket com a GCE, é necessário acessar a instância GCE e entrar na pasta criada, como já demonstrado, e digitar o seguinte comando.

*gsutil rsync gs://<nome do bucket/pasta> .*

O ponto final significa que todos os arquivos no bucket serão armazenados também na pasta da instância criada.

 

------

 

### Sync entre o arquivo da GCE com o bucket

Para sincronizar o arquivo criado na instância com o bucket, é necessário acessar a instância GCE e entrar na pasta criada, como já demonstrado, e digitar o seguinte comando.

*gsutil rsync . gs://<nome do bucket/pasta>*

O ponto final significa que todos os arquivos da instância GCE criada serão sincronizados com o bucket.

 

------

 

### Documentação para sync

Há mais opções de como sincronizar arquivos entre dois serviços diferentes, caso você queira estudar mais sobre ou tenha ficado com alguma dúvida, recomendo a leitura do conteúdo retirado da [documentação oficial da Google](https://cloud.google.com/storage/docs/gsutil/commands/rsync).

 

------

 

**Referências**
Para a escrita desse artigo, a documentação oficial da GCP foi utilizada. [Link de acesso](https://cloud.google.com/docs)
[Google Cloud Platform (GCP) basics in its own words, tutorials and documentations](https://medium.com/tech-digest/google-cloud-platform-gcp-basics-in-its-own-words-tutorials-or-documentations-9f3acd4b68cd)
[Cloud Basics: GCP, Azure and AWS](https://medium.com/@Imaginovation/cloud-basics-gcp-azure-and-aws-8acf4a440052)