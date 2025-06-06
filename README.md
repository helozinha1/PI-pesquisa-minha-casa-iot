# 🔬 Fundamentação Teórica e Pesquisa - Minha Casa IoT

Este documento detalha a pesquisa e a fundamentação teórica que serviram de base para o desenvolvimento do projeto "Minha Casa IoT". Aborda as principais tecnologias, conceitos e considerações que guiaram as escolhas de implementação, visando construir um sistema de automação residencial eficiente, seguro e escalável.

---

## 🚀 Introdução à Automação Residencial (IoT)

A automação residencial, ou "Casa Inteligente" (Smart Home), refere-se à capacidade de controlar e gerenciar dispositivos e sistemas domésticos remotamente ou de forma automatizada, usando a internet e outras tecnologias. O objetivo é aumentar o conforto, a segurança, a eficiência energética e a conveniência dos moradores. O uso de dispositivos conectados (Internet das Coisas - IoT) é o pilar dessa automação, permitindo a comunicação entre objetos físicos e sistemas computacionais.

---

## ⚙️ Tecnologias Chave

Para este projeto, foram selecionadas tecnologias robustas e de código aberto, que oferecem flexibilidade, comunidade ativa e baixo custo de implementação.

### 1. Home Assistant

* **O que é:** Home Assistant é uma plataforma de automação residencial de código aberto que foca na privacidade local e no controle total do usuário. Ele pode ser executado em uma variedade de dispositivos, como Raspberry Pi, tornando-o ideal para soluções caseiras.
* **Vantagens:**
    * **Controle Local:** Prioriza a comunicação e o processamento local, reduzindo a dependência da nuvem e aumentando a privacidade e a velocidade.
    * **Ampla Compatibilidade:** Suporta uma vasta gama de dispositivos e serviços IoT, através de integrações nativas e da comunidade.
    * **Flexibilidade e Automação:** Permite criar automações complexas e personalizadas, adaptando o comportamento da casa às necessidades dos usuários.
    * **Comunidade Ativa:** Possui uma grande comunidade de desenvolvedores e usuários, facilitando o suporte e a busca por soluções.
* **Aplicação no Projeto:** É o cérebro central do sistema "Minha Casa IoT", gerenciando a comunicação entre os dispositivos, executando as automações e fornecendo a interface de usuário.

### 2. MQTT (Message Queuing Telemetry Transport)

* **O que é:** MQTT é um protocolo de mensagens leve, publish/subscribe (publicar/assinar), projetado para conexões de baixa largura de banda e alta latência, ideal para dispositivos IoT com recursos limitados.
* **Funcionamento:**
    * **Broker:** Um servidor central (ex: Mosquitto) que recebe e distribui as mensagens.
    * **Publishers:** Dispositivos que enviam mensagens para um tópico específico (ex: um sensor de temperatura publica a temperatura no tópico `casa/sala/temperatura`).
    * **Subscribers:** Dispositivos ou aplicações que se inscrevem em tópicos para receber mensagens (ex: Home Assistant se inscreve em `casa/sala/temperatura` para exibir o valor).
* **Vantagens:**
    * **Leveza:** Baixo overhead, ideal para microcontroladores e redes com restrições.
    * **Assíncrono:** Não exige que publisher e subscriber estejam conectados simultaneamente.
    * **Eficiência:** Reduz o consumo de bateria e dados.
* **Aplicação no Projeto:** Utilizado como o principal protocolo de comunicação entre o Home Assistant e os dispositivos IoT da casa (como lâmpadas, sensores, TVs, etc.), garantindo uma comunicação eficiente e confiável.

### 3. Raspberry Pi

* **O que é:** Um computador de placa única (Single Board Computer - SBC) de baixo custo e tamanho reduzido, amplamente utilizado em projetos de eletrônica e IoT.
* **Vantagens:**
    * **Custo-benefício:** Solução acessível para rodar servidores de automação.
    * **Versatilidade:** Suporta diferentes sistemas operacionais (incluindo HomeAssistantOS) e possui diversas interfaces (GPIO, USB, Ethernet, Wi-Fi).
    * **Consumo de Energia:** Baixo consumo, ideal para operação contínua.
* **Aplicação no Projeto:** Atua como o hardware principal onde o HomeAssistantOS e o broker MQTT são executados, servindo como o servidor central da casa inteligente.

---

## 🔒 Considerações de Segurança

A segurança é uma preocupação primordial em sistemas IoT. A pesquisa abrangeu as seguintes considerações:

* **Controle Local:** A preferência por soluções com controle local (como Home Assistant) minimiza a exposição de dados à nuvem, reduzindo riscos de vazamento ou acesso não autorizado por terceiros.
* **Autenticação e Autorização:** Implementação de credenciais fortes para acesso ao Home Assistant e ao broker MQTT, além de gerenciamento de usuários.
* **Segmentação de Rede (VLANs):** Embora não explicitamente implementado na camada de software do dashboard, a pesquisa contempla a importância de isolar dispositivos IoT em VLANs separadas para conter possíveis vulnerabilidades e evitar acesso não autorizado a outros segmentos da rede doméstica.
* **Atualizações:** A importância de manter o Home Assistant, o sistema operacional do Raspberry Pi e o firmware dos dispositivos IoT sempre atualizados para corrigir falhas de segurança conhecidas.

---

## 📚 Fontes de Pesquisa e Referências

* **Documentação Oficial do Home Assistant:** [https://www.home-assistant.io/docs/](https://www.home-assistant.io/docs/)
* **Documentação do Protocolo MQTT (MQTT.org):** [https://mqtt.org/](https://mqtt.org/)
* **Artigos sobre Raspberry Pi para IoT:** Diversos blogs e fóruns da comunidade.
* **Livros e Cursos sobre Automação Residencial e Redes.**
* **Artigos e Pesquisas sobre Segurança em IoT.**

---

## 🧑‍💻 Desenvolvido por

* **Gustavo Leite**
* **Helloysa Rocha**
* **Gabrielly Dias**
* **HAGMA**
