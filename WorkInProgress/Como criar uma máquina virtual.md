# Como criar uma máquina virtual

40 minutos1 crédito

## GSP001

## Visão geral

O Compute Engine permite criar máquinas virtuais que executam diversos sistemas operacionais, incluindo vários tipos de Linux (Debian, Ubuntu, Suse, Red Hat e CoreOS) e Windows Server na infraestrutura do Google. Você pode executar milhares de CPUs virtuais em um sistema projetado para ser rápido e oferecer consistência forte no desempenho.

Neste laboratório prático, você vai criar instâncias de máquina virtual de vários tipos usando o console do Google Cloud e a linha de comando `gcloud`. Além disso, você verá como conectar um servidor da Web NGINX à sua máquina virtual.

Em vez de copiar e colar os comandos do laboratório no local adequado, recomendamos que você digite os comandos para reforçar sua compreensão dos conceitos principais.

### Atividades deste laboratório

- Criar uma máquina virtual com o console do Cloud
- Criar uma máquina virtual com a linha de comando `gcloud`
- Implantar um servidor da Web e conectá-lo a uma máquina virtual

### Pré-requisitos

- É recomendável ter familiaridade com os editores de texto padrão do Linux, como `vim`, `emacs` ou `nano`.

## Configuração

## Tarefa 1: crie uma nova instância no console do Cloud

Nesta seção, você vai aprender a criar tipos de máquinas predefinidos usando o Compute Engine no console do Cloud.

1. No console do Cloud, acesse o **Menu de navegação** (![Ícone do menu de navegação](https://storage.googleapis.com/cloud-training/images/menu.png)) e clique em **Compute Engine** > **Instâncias de VM**.

   A primeira inicialização pode levar alguns instantes.

2. Para criar uma instância, clique em **CRIAR INSTÂNCIA**.

3. Você pode configurar muitos parâmetros ao criar uma **instância**. Para este laboratório, use os seguintes parâmetros:

| Campo                      | Valor                                                        | Mais informações                                             |
| :------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| **Nome**                   | **gcelab**                                                   | Nome da instância de VM                                      |
| **Região**                 | `<filled in at lab start>`                                   | Para saber mais sobre as regiões, consulte o guia [Regiões e zonas](https://cloud.google.com/compute/docs/zones) do Compute Engine. |
| **Zona**                   | `<filled in at lab start>` *                                 | **Observação**: lembre da zona selecionada. Você vai precisar dessa informação depois. Para saber mais sobre as zonas, consulte o guia [Regiões e zonas](https://cloud.google.com/compute/docs/zones) do Compute Engine. |
| **Série**                  | **E2**                                                       | Nome da série                                                |
| **Tipo de máquina**        | **2 vCPUs**                                                  | Esta é uma instância de 2 CPUs e 4 GB de RAM (e2-medium). Vários tipos de máquinas estão disponíveis, desde microinstâncias até instâncias com 32 núcleos/208 GB de RAM. Para mais informações, consulte o guia do Compute Engine [Sobre as famílias de máquinas](https://cloud.google.com/compute/docs/machine-types). **Observação**: os projetos novos têm uma [cota de recursos](https://cloud.google.com/compute/docs/resource-quotas) padrão, o que limita o número de núcleos de CPU. Você poderá solicitar uma quantidade maior quando for trabalhar em projetos fora deste laboratório. |
| **Disco de inicialização** | **Novo disco permanente equilibrado de 10 GB** **Imagem do SO: Debian GNU/Linux 11 (bullseye)** | Várias imagens estão disponíveis, por exemplo, Debian, Ubuntu, CoreOS e imagens premium, como Red Hat Enterprise Linux e Windows Server. Para saber mais, consulte a documentação do sistema operacional. |
| **Firewall**               | **Permitir tráfego HTTP**                                    | Selecione esta opção para acessar um servidor da Web que você vai instalar mais tarde. **Observação:** isso criará automaticamente uma regra de firewall para permitir o tráfego HTTP na porta 80. |

1. Clique em **Criar**.

   Levará cerca de um minuto para a máquina ser criada. Depois disso, a nova máquina virtual aparece na página **Instâncias de VM**.

2. Na linha da sua máquina virtual, clique em **SSH**, para se conectar a ela usando **SSH**.

   Isso vai iniciar o cliente SSH diretamente no navegador.

   **Observação**: consulte o guia do Compute Engine [Conectar-se a VMs do Linux usando as ferramentas do Google](https://cloud.google.com/compute/docs/instances/connecting-to-instance). Esse guia tem mais informações sobre como usar o SSH para se conectar a uma instância.

## Tarefa 2: instale um servidor da Web NGINX

Agora você vai instalar um servidor da Web NGINX, um dos servidores mais conhecidos do mundo, para conectar sua máquina virtual a algo.

1. Atualize o SO:

   ```
    sudo apt-get update
   ```

   Copiado.

   content_copy

   **Saída esperada:**

   ```
    Get:1 http://security.debian.org stretch/updates InRelease [94.3 kB]
    Ign http://deb.debian.org strech InRelease
    Get:2 http://deb.debian.org strech-updates InRelease [91.0 kB]
    ...
   ```

2. Instale o **NGINX**:

   ```
    sudo apt-get install -y nginx
   ```

   Copiado.

   content_copy

   **Saída esperada:**

   ```
    Reading package lists… Done
    Building dependency tree
    Reading state information... Done
    The following additional packages will be installed:
    ...
   ```

3. Confirme se o **NGINX está em execução**:

   ```
    ps auwx | grep nginx
   ```

   Copiado.

   content_copy

   **Saída esperada:**

   ```
    root      2330  0.0  0.0 159532  1628 ?        Ss   14:06   0:00 nginx: master process /usr/sbin/nginx -g daemon on; master_process on;
    www-data  2331  0.0  0.0 159864  3204 ?        S    14:06   0:00 nginx: worker process
    www-data  2332  0.0  0.0 159864  3204 ?        S    14:06   0:00 nginx: worker process
    root      2342  0.0  0.0  12780   988 pts/0    S+   14:07   0:00 grep nginx
   ```

4. Para ver a página da Web, volte ao console do Cloud e clique no link **IP externo** na linha da máquina, ou adicione o valor do **IP externo** ao URL `http://EXTERNAL_IP/` em uma nova janela ou guia do navegador.

   Esta página da Web padrão vai aparecer:

   ![Página NGINX padrão](https://www.cloudskillsboost.google/focuses/img/c0908a068b419647.png)

   Clique em **Verificar meu progresso** abaixo para ver até onde você foi neste laboratório. Uma marca de seleção indica que tudo foi feito corretamente.

   Crie uma instância do Compute Engine e adicione um servidor NGINX à instância com as regras de firewall necessárias.

   Verificar meu progresso

## Tarefa 3: crie uma nova instância com a gcloud

Em vez de usar o console do Cloud para criar uma instância de máquina virtual, você pode usar a ferramenta de linha de comando `gcloud`, que vem pré-instalada no [Google Cloud Shell](https://cloud.google.com/developer-shell/#how_do_i_get_started). O Cloud Shell é uma máquina virtual baseada em Debian. Ele contém todas as ferramentas de desenvolvimento necessárias (`gcloud`, `git`, entre outras) e oferece um diretório principal permanente de 5 GB.

**Observação**: se você quiser testar esse processo no seu computador, leia o [guia da ferramenta de linha de comando gcloud](https://cloud.google.com/sdk/gcloud/).

1. No Cloud Shell, use o comando `gcloud` para criar uma instância de máquina virtual na linha de comando:

   ```
        gcloud compute instances create gcelab2 --machine-type e2-medium --zone 
   ```

   Copiado.

   content_copy

   **Saída esperada:**

   ```
        Created [...gcelab2].
        NAME: gcelab2
        ZONE:  
        MACHINE_TYPE: e2-medium
        PREEMPTIBLE:
        INTERNAL_IP: 10.128.0.3
        EXTERNAL_IP: 34.136.51.150
        STATUS: RUNNING
   ```

   Clique em **Verificar meu progresso** abaixo para ver até onde você foi neste laboratório. Uma marca de seleção indica que tudo foi feito corretamente.

   Crie uma nova instância com a gcloud.

   Verificar meu progresso

   Os valores padrão da nova instância são estes:

   - A imagem mais recente do [Debian 11 (bullseye)](https://cloud.google.com/compute/docs/images#debian)
   - O [tipo de máquina](https://cloud.google.com/compute/docs/machine-types) `e2-medium`
   - Um disco permanente raiz com o mesmo nome da instância. O disco é automaticamente anexado a ela

   Durante seu trabalho, é possível especificar um [tipo de máquina personalizado](https://cloud.google.com/compute/docs/instances/creating-instance-with-custom-machine-type).

2. Para ver todos os padrões, execute o seguinte:

   ```
    gcloud compute instances create --help
   ```

   Copiado.

   content_copy

   **Observação**: se você trabalha sempre na mesma região/zona e não quer anexar a flag `--zone` todas as vezes, recomendamos que defina a região e as zonas padrão que a `gcloud` usa.

   Para fazer isso, execute estes comandos:

   `gcloud config set compute/zone ...`

   `gcloud config set compute/region ...`

3. Para sair de `help`, pressione **CTRL+C**.

4. Abra o **Menu de navegação** no console do Cloud e clique em **Compute Engine > Instâncias de VM** para conferir as duas novas instâncias.

5. Você também pode usar o SSH para se conectar à sua instância usando a `gcloud`. Adicione a zona ou omita a flag `--zone` se tiver definido a opção globalmente:

   ```
        gcloud compute ssh gcelab2 --zone  
   ```

   Copiado.

   content_copy

6. Digite **Y** para continuar.

   ```
      Do you want to continue? (Y/n)
   ```

7. Pressione **ENTER** na seção de senha longa para deixar esse campo em branco.

   ```
      Generating public/private rsa key pair.
      Enter passphrase (empty for no passphrase)
   ```

8. Depois de se conectar, saia do shell remoto para se desconectar do SSH:

   ```
    exit
   ```

   Copiado.

   content_copy

## Tarefa 4: teste seus conhecimentos

Faça nosso teste para avaliar seus conhecimentos sobre o Google Cloud. Selecione mais de uma opção se necessário.



Through which of the following ways can you create a VM instance in Compute Engine?



The Cloud Console



The gcloud command line tool

Enviar



## Parabéns!

O Compute Engine é a base da infraestrutura como serviço do Google Cloud. Você criou uma máquina virtual com o Compute Engine e agora pode adequar a infraestrutura de servidores, a topologia de rede e os balanceadores de carga ao Google Cloud.

### Termine a Quest

Este laboratório autoguiado faz parte da Quest [Google Cloud Essentials](https://google.qwiklabs.com/quests/23). Uma Quest é uma série de laboratórios relacionados que formam um programa de aprendizado. Inscreva-se [nessa Quest](https://google.qwiklab.com/learning_paths/23/enroll) e receba crédito de conclusão imediatamente por fazer este laboratório. [Veja outras Quests disponíveis](https://google.qwiklabs.com/catalog).

#### Comece o próximo laboratório

Continue sua Quest em [Para começar com o Cloud Shell e a gcloud](https://www.cloudskillsboost.google/focuses/563?locale=pt_BR&parent=catalog) ou confira estes laboratórios do Google Cloud Ensina:

- [Provisionar serviços com o Google Cloud Marketplace](https://www.cloudskillsboost.google/focuses/565?locale=pt_BR&parent=catalog)

### Próximas etapas / Saiba mais

- Para conferir uma visão geral das VMs, acesse [Instâncias de máquina virtual](https://cloud.google.com/compute/docs/instances/).
- Veja como [migrar VMs para o Google Cloud](https://cloud.google.com/migrate/).
- Saiba mais sobre [topologia de rede e sub-redes](https://cloud.google.com/compute/docs/networking).
- Para usar o tipo certo de máquina virtual, leia o artigo [Como escolher um tipo de VM](https://cloud.google.com/datalab/docs/how-to/machine-type).