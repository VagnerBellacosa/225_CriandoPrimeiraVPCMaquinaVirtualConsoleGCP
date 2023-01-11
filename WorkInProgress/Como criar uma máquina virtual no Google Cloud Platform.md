# Como criar uma máquina virtual no Google Cloud Platform

A maneira mais simples de iniciar com a Computação em Nuvem, é através de uma máquina virtual, porque é o que a maioria dos TIs está acostumado. Uma máquina virtual, é nada mais que um servidor a disposição, sem a manuntenção necessária de um servidor físico.

O Google Cloud Platform possui um serviço chamado Google Compute Engine que basicamente é um serviço voltado a máquinas virtuais. Tem muito lá, mas a maneira mais fácil de iniciar o serviço é criando uma máquina virtual.

Para poder criar uma máquina virtual é necessário que tenhas permissões por meio de uma role para administrar VMs (*virtual machines*). Ou ter o role de Project Owner ou Project Editor (apesar de não ser o recomendado em empresas grandes). Sempre bom manter o princípio de “Least Privillege”, que prega que um usuário só deve ter as permissões necessárias para fazer o seu trabalho, nada além disso.

Sem mais papo. Vamos iniciar.

1. Abra a consola do GCP c[onsole.cloud.google.com](http://console.google.cloud.com/)

![img](https://miro.medium.com/max/700/1*Mg2WtrMmzH1I6-Vnu4dWpQ.png)

\2. Na secção Compute, no sub-menú “Compute Engine”, clique VM Instances

![img](https://miro.medium.com/max/618/1*Asvyt_ocAO3K_2noYLqyQw.png)

\3. Isso vai abrir a página do serviço Google Compute Engine. Noo lado esquerdo existem outros produtos do serviço. Por agora, clique em “create”

![img](https://miro.medium.com/max/587/1*WPpVqNGumElbPPWE5y2IHw.png)

\4. Aqui é o onde se realmente cria uma Máquina virtual. Vamos analisar o que cada campo significa.

![img](https://miro.medium.com/max/590/1*VtdsLxCfxO0JEznvgarxzg.png)

O Nome diz respeito ao nome único (a sua rede, esse é um assunto para outro artigo, porém todo projecto GCP vem com uma rede criada e configurada para si) que será atribuído à sua VM. Este nome, para além de identificar a sua VM, poderá depois ser usado pelo DNS local, por outras máquinas na sua rede.

A região indica a área geográfica onde a sua máquina estará localizada. A zona indica exatamente onde dentro da região, a máquina vai estar localizda. Uma região é composta por múltiplas zonas.

\5. Escolha o tipo de VM que precisa, pode escolher a RAM e o número de vCPUS (duas vCPUS correspondem a uma CPU física). Existem três tipos de configuração que são as “de propósito geral”, as “optimizadas para computação, com um maior rácio vCPUS/RAM” e as “optimizadas para memória com maior rácio RAM/vCPUS”. O predefinido é o de propósito geral que vem com 4GB de RAM e 2 vCPUs.

![img](https://miro.medium.com/max/588/1*WmC1gjEphnacTHY0iA_eyQ.png)

\6. O Boot Disk te permite escolher um disco para bootável, com um SO. Se clicar em Change, poderá escolher um SO Windows ou Linux. Atenção que Windows Server incorre cobranças de lincença.

![img](https://miro.medium.com/max/596/1*JEdrrEWoRth5IlOofca2AQ.png)

\7. Aqui indicamos o acesso a serviços GCP que a VM terá. Seleccione em **Allow full access to all Cloud APIs**. Esta opção vai dar acesso a todos os serviços do GCP a VM por meio do service account. Se for a usar a VM para servir de host de um web server, pode habilitar as opções que permite trafégo HTTP/HTTPS. Deixe o resto como está.

![img](https://miro.medium.com/max/610/1*3Ha4pLeDB-ecnAGyALN_hA.png)

E clique em criar, e espere uns minutos e já está!

![img](https://miro.medium.com/max/700/1*7M8SS-9MrsU6hcgKX0x6wA.png)

Nossa VM recé-criada

Para ter acesso SSH, é só clicar em SSH que a Google trata do resto para si. Sem configuração necessária.

Para apagar é só selecionar a checkbox da VM e na parte superior clicar no símbolo da lata de lixo e confirmar.

[Compute Engine](https://medium.com/tag/compute-engine?source=post_page-----a99811e5fef5---------------compute_engine-----------------)

[Google Cloud Platform](https://medium.com/tag/google-cloud-platform?source=post_page-----a99811e5fef5---------------google_cloud_platform-----------------)

[Virtualization](https://medium.com/tag/virtualization?source=post_page-----a99811e5fef5---------------virtualization-----------------)













## [More from GDG Maputo](https://medium.com/android-dev-moz?source=post_page-----a99811e5fef5--------------------------------)

Follow

Artigos em português, escritos pela comunidade GDG Maputo. Faça parte da nossa comunidade: https://www.meetup.com/GDG-Maputo/

[![Igor L Sambo💙🇲🇿](https://miro.medium.com/fit/c/24/24/2*sBBSw3ymmzQYgZFj-szEDQ.jpeg)](https://medium.com/@LSambo02?source=post_page-----a99811e5fef5----0----------------------------)[Igor L Sambo💙🇲🇿](https://medium.com/@LSambo02?source=post_page-----a99811e5fef5----0----------------------------)[·Jun 9, 2020](https://medium.com/android-dev-moz/pub-get-vs-pub-upgrade-descomplicar-o-que-já-é-descomplicado-9ab5999bc6ba?source=post_page-----a99811e5fef5----0----------------------------)[Pub Get vs Pub Upgrade — Descomplicar o que já é descomplicado!Este artigo aborda dois conceitos bastante simples, porém geram alguma confusão e são usados quando não é necessário (como eu rsrsrs)…! No caso são as acções do pub get e o pub upgrade que servem para “resolver” as dependências que nós queremos em nosso projecto, e é isso! Obrigado… Mas como funcionam?](https://medium.com/android-dev-moz/pub-get-vs-pub-upgrade-descomplicar-o-que-já-é-descomplicado-9ab5999bc6ba?source=post_page-----a99811e5fef5----0----------------------------)[Flutter](https://medium.com/tag/flutter?source=post_page-----a99811e5fef5---------------flutter-----------------)[4 min read](https://medium.com/android-dev-moz/pub-get-vs-pub-upgrade-descomplicar-o-que-já-é-descomplicado-9ab5999bc6ba?source=post_page-----a99811e5fef5----0----------------------------)[![Pub Get vs Pub Upgrade — Descomplicar o que já é descomplicado!](https://miro.medium.com/fit/c/112/112/1*joSdXKP5ns54DEDKX4qrVw.png)](https://medium.com/android-dev-moz/pub-get-vs-pub-upgrade-descomplicar-o-que-já-é-descomplicado-9ab5999bc6ba?source=post_page-----a99811e5fef5----0----------------------------)Share your ideas with millions of readers.[Write on Medium](https://medium.com/new-story?source=post_page_footer_cta_write-------------------------------------)[![Calleb Miquissene](https://miro.medium.com/fit/c/24/24/0*kzc9L7IGGNxJjTw4)](https://medium.com/@callebdev?source=post_page-----a99811e5fef5----1----------------------------)[Calleb Miquissene](https://medium.com/@callebdev?source=post_page-----a99811e5fef5----1----------------------------)[·Jun 7, 2020](https://medium.com/android-dev-moz/lidando-com-usuários-ou-clientes-40dd295b9de3?source=post_page-----a99811e5fef5----1----------------------------)[Lidando com usuários ou clientesA primeira vez que você mostra aos usuários um protótipo funcional do seu aplicativo pode ser fantástico, porém assustador. E se eles criticarem ou simplesmente não gostarem? Lembre-se de que os usuários não estão a criticar você; eles estão a criticar sua teoria do design. Você deve ser receptivo a todos os comentários neste momento e, depois de…](https://medium.com/android-dev-moz/lidando-com-usuários-ou-clientes-40dd295b9de3?source=post_page-----a99811e5fef5----1----------------------------)[Clientes](https://medium.com/tag/clientes?source=post_page-----a99811e5fef5---------------clientes-----------------)[2 min read](https://medium.com/android-dev-moz/lidando-com-usuários-ou-clientes-40dd295b9de3?source=post_page-----a99811e5fef5----1----------------------------)[![Lidando com usuários ou clientes](https://miro.medium.com/fit/c/112/112/1*HvsvmSPfvj_utey7gZmMfw.png)](https://medium.com/android-dev-moz/lidando-com-usuários-ou-clientes-40dd295b9de3?source=post_page-----a99811e5fef5----1----------------------------)[![Igor L Sambo💙🇲🇿](https://miro.medium.com/fit/c/24/24/2*sBBSw3ymmzQYgZFj-szEDQ.jpeg)](https://medium.com/@LSambo02?source=post_page-----a99811e5fef5----2----------------------------)[Igor L Sambo💙🇲🇿](https://medium.com/@LSambo02?source=post_page-----a99811e5fef5----2----------------------------)[·May 26, 2020](https://medium.com/android-dev-moz/gerenciamento-de-estado-mobx-f7934c96682e?source=post_page-----a99811e5fef5----2----------------------------)[Gerenciamento de estado — MobxDepois de tantas opções de gerenciamento de estado, porquê conhecer outro? Será que os anteriores não são bons? Será que o Mobx é melhor? Estas e mais perguntas podem estar surgindo em seu cérebro, mas como desenvolvedores (e não só) sabemos que em termos de soluções para um problema/situação depende…](https://medium.com/android-dev-moz/gerenciamento-de-estado-mobx-f7934c96682e?source=post_page-----a99811e5fef5----2----------------------------)[Flutter](https://medium.com/tag/flutter?source=post_page-----a99811e5fef5---------------flutter-----------------)[4 min read](https://medium.com/android-dev-moz/gerenciamento-de-estado-mobx-f7934c96682e?source=post_page-----a99811e5fef5----2----------------------------)[![Gerenciamento de estado —  Mobx](https://miro.medium.com/fit/c/112/112/1*RlgQqhspnz4daR2QQghgAw.png)](https://medium.com/android-dev-moz/gerenciamento-de-estado-mobx-f7934c96682e?source=post_page-----a99811e5fef5----2----------------------------)[![Igor L Sambo💙🇲🇿](https://miro.medium.com/fit/c/24/24/2*sBBSw3ymmzQYgZFj-szEDQ.jpeg)](https://medium.com/@LSambo02?source=post_page-----a99811e5fef5----3----------------------------)[Igor L Sambo💙🇲🇿](https://medium.com/@LSambo02?source=post_page-----a99811e5fef5----3----------------------------)[·May 26, 2020](https://medium.com/android-dev-moz/state-management-bloc-edb9c9342d8f?source=post_page-----a99811e5fef5----3----------------------------)[Gerenciamento de estado — BLoCEste provavelmente, será um artigo muito curto, primeiro porque há que esclarecer que o BLoC é mais um padrão que um gestor de estado de concreto, este pode ser combinado com outra abordagens de gerenciamento de estado. Apenas isso! Mas ok! O que é o BLoC concretamente? …](https://medium.com/android-dev-moz/state-management-bloc-edb9c9342d8f?source=post_page-----a99811e5fef5----3----------------------------)[Flutter](https://medium.com/tag/flutter?source=post_page-----a99811e5fef5---------------flutter-----------------)[4 min read](https://medium.com/android-dev-moz/state-management-bloc-edb9c9342d8f?source=post_page-----a99811e5fef5----3----------------------------)[![Gerenciamento de estado — BLoC](https://miro.medium.com/fit/c/112/112/1*RlgQqhspnz4daR2QQghgAw.png)](https://medium.com/android-dev-moz/state-management-bloc-edb9c9342d8f?source=post_page-----a99811e5fef5----3----------------------------)[![Igor L Sambo💙🇲🇿](https://miro.medium.com/fit/c/24/24/2*sBBSw3ymmzQYgZFj-szEDQ.jpeg)](https://medium.com/@LSambo02?source=post_page-----a99811e5fef5----4----------------------------)[Igor L Sambo💙🇲🇿](https://medium.com/@LSambo02?source=post_page-----a99811e5fef5----4----------------------------)[·May 26, 2020](https://medium.com/android-dev-moz/state-management-redux-f12760cd6a22?source=post_page-----a99811e5fef5----4----------------------------)[Gerenciamento de estado — ReduxPor esta altura já somos experts em gerenciamento de estado, mas ainda há mais opções e esta é óptima quando se pretende actualizar estados globais de uma aplicação deixando este disponível para aceder de qualquer ponto de nossa aplicação. Este artigo faz parte de uma série de 5 artigos que…](https://medium.com/android-dev-moz/state-management-redux-f12760cd6a22?source=post_page-----a99811e5fef5----4----------------------------)[Flutter](https://medium.com/tag/flutter?source=post_page-----a99811e5fef5---------------flutter-----------------)[3 min read](https://medium.com/android-dev-moz/state-management-redux-f12760cd6a22?source=post_page-----a99811e5fef5----4----------------------------)[
  ](https://medium.com/android-dev-moz/state-management-redux-f12760cd6a22?source=post_page-----a99811e5fef5----4----------------------------)