# Criando a máquina

Para começarmos, precisamos primeiramente de uma máquina para podermos instalar o sistema operacional que será investigado, para facilitar o trabalho de coleta de dados optei por usar uma máquina virtual utilizando o software [VirtualBox](https://www.virtualbox.org/) na versão 7.0.8 r156879 (Qt5.15.3).

Na primeira tela da criação da máquina virtual selecionei **Pular Instalação Desassistida**, pois se desmarcada o windows será configurado automaticamente na instalação.

![screen_1](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/9fa32574-8e68-4ab6-a3d3-026cf76dc723)

Aqui coloquei **4,2g** de memória pois o windows 11 não aceita menos que **4g** para instalar o sistema, e em **CPU** coloquei apenas 3.

![screen_2](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/d6938bc8-259d-4a63-8c84-78c878ee479e)

No tamanho de disco coloquei 50g, você pode colocar mais se quiser.

![screen_3](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/e5ffe615-89af-4cef-a98f-f5bdaecc2e40)

Aqui é um resumo das configurações da máquina

![screen_4](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/c5e56812-5980-45b1-b60a-d039733c9a44)

![screen_5](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/72de78c4-57e8-4eb3-9204-0ca322f762e9)

Agora vamos configurar a rede da nossa máquina, onde vamos deixar a placa em **modo bridge** e aproveitar para salvar o **endereço MAC** da máquina, pois será com ele que vamos filtrar os pacotes de rede.

![image](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/103b6ef6-7d12-41c1-a0f7-47f51e7cee9b)

# Iniciando instalação e captura dos dados

## Capturando dados

Antes de iniciar a máquina virtual foi iniciado a captura dos dados com a ferramenta [Wireshark](https://www.wireshark.org/) onde configurei o filtro para mostrar somente o trafego do MAC da máquina virtual, pois como eu estava pegando o trafego da minha placa de rede WiFi iria aparecer todo o trafego do meu computador misturado com a da máquina virtual e fazendo isso consigo isolar o trafego. após tudo configurado partimos para a instalação.

![image](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/8a05f18f-0e0a-4a00-8f2f-6ece12eeb03d)

![image](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/061a5f4d-24e6-4927-8b2a-44d4cd4f0e52)

## Instalando OS

Nessa parte da instalação irei mostar os passos e **configurações** que utilizei na instalação do sistema, e comentar algums pontos observados durante a **captura dos pacotes**.

Essa primeira parte não alterei nada, apenas cliquei em `Avançar`.

![screen_8](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/d1e9701d-16db-4ba7-98d3-932fd69461f2)

Apenas cliquei em `Instalar Agora`.

![screen_9](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/48ca530b-9c32-46f9-bcce-ac5cd07dbe09)

![screen_10](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/3219db8b-36ec-4352-808e-219d65b4ba01)

Aqui cliquei em `Não tenho a chave do produto`

![screen_11](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/13e13c1d-6918-4de9-a2fe-396d7454b180)

Nessa tela selecionei a versão **Windows 11 Pro** e cliquei em `Avançar`

![screen_12](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/93a1a590-1c27-4fd4-b2c5-51b5351254bb)

Aqui eu aceitei os termos e cliquei em `Avançar`

![screen_13](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/ab43d4a6-22f6-4e73-8e74-66d6286d0b19)

Nessa tela selecionei **Personalizada**

![screen_14](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/b804d966-af8a-4588-a77b-875000900f81)

Selecionei a memória disponível e cliquei em `Avançar`

![screen_15](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/53346b3f-b03e-42f3-8e8c-e4150095a6b4)

Aguardei a instalação concluir

![screen_16](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/2474a63d-7eb8-45b2-9b15-2b77cf894db2)

![screen_17](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/5094a3d7-6b1e-47b6-970d-8925d1a16af1)

> :warning: Aqui termina a instalação do sistema, até aqui não foi observado nenhum trafego de rede desta máquina durante essa etapa.

## Configurações iniciais do sistema

Ao iniciar o sistema já foi obsevado um pequeno trafego de rede.

![screen_18](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/b18b3135-f635-4194-be1d-5a959645b719)

![screen_19](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/e9a29ed2-a14c-439b-87ad-e27249256f29)

![screen_20](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/4e3a0cb1-213e-4445-86b5-deef9061ca43)

Nessa etapa de inicialização foi observado um volume muito grande de trafego de dados, essa parte foi a que observei o maior volume de dados durante todo o processo. Apartir daqui também foi observado um trafego contante até a inicialização de fato do sistema.

Nessa tela selecionei **Brasil** e cliquei em `Sim`

![screen_22](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/34bf45c4-4fb7-40ca-a3d3-a447c352e1c8)

Aqui cliquei apenas em **Sim**

![screen_23](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/f3ca7939-6f41-4aa6-b4e3-cc3f34310f64)

Nessa tela cliquei em `Pular`

![screen_24](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/8505e697-1912-45bc-b0da-94bd140a5fc6)

Aqui aguardei atualizar e reiniciar

![screen_25](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/028c29c5-01e4-46cf-bdb1-a76cf72f3bc4)

![screen_26](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/80be91b3-2355-4bb6-aa3f-38cec2099e47)

![screen_27](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/7dc0f31c-241a-4721-a222-27e6025c9f54)

![screen_28](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/c7aadda7-6d2c-411a-a447-130569a4f2ec)

Aqui apenas coloquei o nome e cliquei em `Avançar`

![screen_29](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/f16373e0-6386-4c93-a5f5-ac129e9140db)

Aguardei

![screen_30](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/9c0864ea-d2a8-451f-9f36-22cf296d4cdc)

Aqui selecionei **Configurar para uso pessoal** e cliquei em `Próximo`

![screen_31](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/d56cdc7f-868a-4827-be40-6e35fc48210d)

Cliquei em `Entrar`

![screen_32](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/aee66a49-d06b-4f35-addf-70a54c859965)

Coloquei um email aleatório apenas para poder passar sem fazer login e cliquei em `Próximo`

![screen_33](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/92b33db8-659e-4025-bd91-2729f270b82b)

Fiz a mesma coisa aqui e cliquei em `Próximo`

![screen_34](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/00074454-1e9a-468e-9322-f2a9b28b7abd)

Cliquei em `Próximo`

![screen_35](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/03058ca4-5848-4434-9bf2-abc612cbc23f)

Escrevi o nome de usuário e cliquei em `Avançar`

![screen_36](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/5043425c-db85-4680-b16f-b7c5938e51c9)

Apenas cliquei em `Avançar`

![screen_37](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/8871c4a3-9319-48ff-bfa7-8fb81a08a364)

## Permições do sistema

Nessa etapa apenas selecionei as permições que **negava** ou **restringia** o uso dos meus dados

> :warning: Atenção! <br> Foi feito duas capturas onde uma foi **negando** e **restringindo** tudo que podia e a outra foi **permitindo** tudo, como os passos que segui foram os mesmo mudando apenas essa etapa de um para o outro as configurações utilizada permitindo tudo está no final dessa página.

Selecionei **Não**

![screen_39](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/b1a4208c-2a1b-4bb8-8a02-8f9a038c20ac)

Selecionei **Não**

![screen_41](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/c2864deb-b746-4480-b677-f769c9d4bb4c)

Selecionei **Apenas Obrigatórios**

![screen_43](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/9fc8bfe0-8df1-4d80-9bf8-787cf758d4cd)

Selecionei **Não**

![screen_45](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/3641d245-bab2-4433-813a-2931f2371940)

Selecionei **Não**

![screen_47](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/fe90c63d-9770-40b5-9ce3-a4230b38085e)

Selecionei **Não**

![screen_49](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/2e577b9d-51f9-47ea-8849-8096699011c5)

Aguardei atualizar e reiniciar

![screen_50](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/6083f576-9acc-4265-b67d-e0ebba351be6)

## Iniciando sistema configurado

Nessa etapa não tem muito segredo apenas esperei inicar

![screen_51](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/3e390ebf-570a-496b-a062-d34eaa569bcf)

![screen_52](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/8a9b742f-4d1f-4259-9a1f-334ae3be7f19)

![screen_53](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/04c49b48-76ea-448e-a008-139b846a0eef)

## Utilizando o sistema

Nessa etapa apenas configurei o monitor para não desligar e deixei a maquina aberta sem fazer mais nada. Nessa parte observei um trafego logo no inicio mais depois de algum tempo o trafego diminuiu ao ponto de em algums momentos zerar. Apartir daqui foi capturado mais 60 minutos de trafego sem fazer mais nada.

Cliquei em `Configurações`

![screen_54](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/c178527b-8dfa-43c4-9254-60bb8128eee5)

![screen_55](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/626c6a73-ff9b-4e25-92da-06c8ef2d7ed1)

Cliquei em `Energia e bateria`

![screen_56](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/cd86ac5a-13d3-45b3-b86e-9cc1d83895e8)

Selecionei **Tela e suspensão** para `Nunca`, apenas para que a máquina não desligasse a tela e suspendece os processos

![screen_57](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/4612d248-f12c-4768-8bce-d62c534425fd)

Aguardei 60 minutos

![screen_58](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/862c4326-5ae7-4bae-8964-e8c12a1555d4)

## Mostrando versão do windows

![screen_59](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/6e02da2b-2697-4e0f-bcb3-fe92666d1ff5)

## Configurações permitindo tudo

> :warning: Atenção! <br> Foi feito duas capturas onde uma foi **negando** e **restringindo** tudo que podia e a outra foi **permitindo** tudo, como os passos que segui foram os mesmo mudando apenas essa etapa de um para o outro as configurações utilizada **negando** e **restringindo** tudo está na etapa **Permições do sistema** dessa página.

Em todo o processo onde permiti tudo e após isso aguardei os 60 minutos sem fazer nada, não observei diferença no volume de trafego de uma configuração para a outra.

Selecionei **Sim**

![screen_38](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/5c483082-355c-40ed-ba9f-030462d86693)

Selecionei **Sim**

![screen_40](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/f78e7665-5bac-4410-92a9-30692a93a87d)

Selecionei **Incluir Opcionais**

![screen_42](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/f0df743b-d384-472c-9bff-4d4629589a39)

Selecionei **Sim**

![screen_44](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/c69abac1-5a67-46e4-b760-24628e975a39)

Selecionei **Sim**

![screen_46](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/4eee09e0-7de8-404c-9578-072cc1646e51)

Selecionei **Sim**

![screen_48](https://github.com/Elvis-Almeida/privacidade-no-windows-11/assets/70353348/9510916a-46a5-4ddc-906b-d9137b83d298)

> :warning: Atenção! <br> Após terminado todo os processos de captura, foram salvos todos os trafegos da sequinte forma: **permitindo tudo** filtrado pelo IP da máquina vitual (_o IP foi encontrado apenas vendo os primeiros pacotes com o filtro de MAC_) e filtrado por MAC e **negando e restringindo tudo** filtrado pelo IP e por MAC. onde o total deu mais de **1g** de trafego.
