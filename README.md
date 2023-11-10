
# Estudo de Microsservices para Venda de Ingressos - CineTicket

<!-- 
    Logo image generated by Bing IA: https://www.bing.com/images/create/
    Font file by dafont: https://www.dafont.com/pt/cinema-st.font?text=CineTicket&psize=l
-->
<img 
  src="./docs/images/header.png" 
/>

<img src="./docs/images/icons/nginx.svg" width="25px" height="25px" title="Nginx" alt="Nginx"> <img src="./docs/images/icons/nodedotjs.svg" width="25px" height="25px" title="Node.js" alt="Node.js"> <img src="./docs/images/icons/npm.svg" width="25px" height="25px" alt="npm" title="npm"> <img src="./docs/images/icons/express.svg" width="25px" height="25px" title="Express" alt="Express"> <img src="./docs/images/icons/docker.svg" width="25px" height="25px" alt="Docker" title="Docker"> <img src="./docs/images/icons/github.svg" width="25px" height="25px" alt="GitHub" title="GitHub"> <img src="./docs/images/icons/nx.svg" width="25px" height="25px" alt="NX" title="NX"> <img src="./docs/images/icons/visualstudiocode.svg" width="25px" height="25px" alt="vscode" title="vscode"> <img src="./docs/images/icons/bootstrap.svg" width="25px" height="25px" alt="bootstrap" title="bootstrap"> <img src="./docs/images/icons/jquery.svg" width="25px" height="25px" alt="jquery" title="jquery"> <!-- icons by https://simpleicons.org/?q=types -->

![Badge Status](https://img.shields.io/badge/STATUS-EM_DESENVOLVIMENTO-green)


 [![Miro](https://img.shields.io/badge/VISIT%20OUR-MIRO-050038?style=for-the-badge&logo=MIRO&logoColor=white)](https://miro.com/app/board/uXjVNRofMoA=/) [![Youtube](https://img.shields.io/badge/API%20Event%20storming%20PTBR-Youtube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/watch?v=6nEbm71Vc3w) [![Github Project](https://img.shields.io/badge/PROJECT%20VIEW-GITHUB-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/users/jtonynet/projects/2)


<br/>

#### 🕸️ Minhas Redes:
[![linkedin](https://img.shields.io/badge/Linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jos%C3%A9-r-99896a39/) [![dev.to](https://img.shields.io/badge/dev.to-0A0A0A?style=for-the-badge&logo=devdotto&logoColor=white)](https://dev.to/learningenuity) [![gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:learningenuity@gmail.com) [![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/aromademirtilo) [![instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/learningenuity) 


---

<a id="indice"></a>
## :arrow_heading_up: Índice
<!--ts-->

[Estudo de Microsservices para Venda de Ingressos - CineTicket](#estudo-de-microsservices-para-venda-de-ingressos---cineticket)<br/>
  :arrow_heading_up: [Índice](#arrow_heading_up-índice)<br/>
  :green_book: [Sobre](#green_book-sobre)<br/>
  :camera: [Imagens](#camera-imagens)<br/>
  :computer: [Instalação](#computer-instalação)<br/>
  :bar_chart: [Diagramas](#bar_chart-diagramas)<br/>
  :hammer: [Ferramentas](#hammer-ferramentas)<br/>
  :clap: [Boas Práticas](#clap-boas-práticas)<br/>
  :nerd_face: [Para Desenvolvedores](#nerd_face-para-desenvolvedores)<br/>
  :1234: [Versões](#1234-versões)<br/>
  :robot: [Uso de IA](#ia)

<!--te-->
---
<a id="sobre"></a>
## :green_book: Sobre

Monorepo para estudo de arquitetura de venda de ingressos similar ao video ["Como fazer o ingressos.x escalar?"](https://www.youtube.com/watch?v=0TMr8rsmU-k)

Não busco as melhores soluções nem o cenário perfeito (tudo sempre tem trade-offs). Pretendo resolver questões específicas e criar "APIs Mock" para serviços, com o objetivo de validar hipóteses e aos poucos escalar para algo totalmente funcional.

Isso é um laboratório de utilização de serviços para solucionar os dois principais problemas propostos pelo video:
1. Como escalar uma funcionalidade que possui um gargalo do lado do principal fornecedor (a API de reserva de tickets).
2. Criar uma "antesala" que impeça um "flood" de requisições semelhante a um ataque DDoS.

Além dos mencionados, trabalhar com consistência eventual e implementar um conjunto de "rollbacks" de reserva caso ocorram falhas no pagamento ou na reserva (nas APIs externas "mock"). Tentar evoluir a solução para algo semelhante ao padrão de saga.

Devo criar o projeto aumentando aos poucos seu escopo do zero ao deploy.

Foi utilizado o [template bootstrap gratuito FlixGo](https://www.templateshub.net/template/FlixGo-Online-Movies-Template), algumas alterações serão necessárias, pois o mesmo foi elaborado tendo sistemas de streaming em mente. A princípio, usando JavaScript puro para chamadas de API, aos poucos sendo alteradas para componentes React, aproveitando a versatilidade do gerenciador de monorepos Nx.

Pretendo construir os serviços do sistema distribuído em Node.js e Go e utilizar [Architecture decision record (ADR)](https://github.com/joelparkerhenderson/architecture-decision-record) para justificar as tomadas de decisão.

[:arrow_heading_up: voltar](#indice)

---

<a id="imagens"></a>
## :camera: Imagens
Projeto rodando local
<img src="./docs/images/project.png" alt="Projeto rodando local" title="Projeto rodando local"> 

<br>

[:arrow_heading_up: voltar](#indice)

---

<a id="instalacao"></a>
## :computer: Instalação

Para executar o projeto, siga as instruções abaixo:

1. Faça o download/clone do repositório do projeto.
2. Certifique-se de ter o Docker Compose instalado em sua máquina.
3. Execute na raiz do projeto, o comando `docker-compose up` ou `docker compose up`, dependendo da versão do Docker Compose instalada.
4. Acesse `http://localhost:8080` em seu navegador para visualizar o projeto.

[:arrow_heading_up: voltar](#indice)

---

<a id="diagrama"></a>
## :bar_chart: Diagramas

O diagrama abaixo ilustra a uma **proposta** de arquitetura para o projeto:

```mermaid
graph LR

subgraph USER FLOW
  A([Web Client]) -->|HTTP| B(front-site catalog view)
  A -->|HTTP| D(front-site authentication)
  D -->|HTTP| C(front-site purchase)
end

subgraph BACKEND
  subgraph API
    B -->|HTTP| E[catalog-service]
    C -->|HTTP| N[orchestration-service]
    N -->|GRPC| F[checkout-service]
    N -->|GRPC| L[ticket-reservation-service]
    D <-->|HTTP| O[authorization-service]
  end
  
  subgraph DATABASE
    H[(catalog-service DB)] <-->| | E
    K[(checkout-service DB)] <-->| | F
    P[(authorization-service DB)] <-->| | O
    Q[(ticket-reservation-service DB)] <-->| | L
  end
  
  subgraph CACHE
    E <-->| | R[redis-catalog-cache]
  end

  subgraph MOCK-EXTERNAL-APIs
    F -->|HTTP| G[mock-payment-gateway-x-service]
    L -->|HTTP| M[mock-provider-x-reservation-slow-service]
  end
end
``` 

<br>
<details>
<summary>O fluxo de interações para o usuário comprar um assento de um filme que esteja sendo exibido, com base no diagrama fornecido, é o seguinte:</summary>
<br/>
<ol>
  <li>
    Acesso à visualização do cine-ticket-front-site: O usuário pode acessar a interface de visualização do cine-ticket-front-site (representado pela seta "Cliente Web" -> "cine-ticket-front-site visualizacao").
  </li>
  <li>
    Autenticação no cine-ticket-front-site: O usuário pode realizar o processo de autenticação no cine-ticket-front-site (representado pela seta "Cliente Web" -> "cine-ticket-front-site autenticacao" -> "cine-ticket-user-auth-api").
  </li>
  <li>
    Compra no cine-ticket-front-site: Após a autenticação, o usuário pode prosseguir com a compra no cine-ticket-front-site (representado pela seta "Cliente Web" -> "cine-ticket-front-site compra" -> "cine-ticket-orchestration-api" -> "cine-ticket-checkout-api" -> "mock-gateway-pagamento-api" e "cine-ticket-confirma-reserva" -> "mock-parceiro-reserva-lento-api").
  </li>
</ol>
<br>
  Dessa forma, o fluxo completo de interações envolve o cliente web interagindo com as APIs de exibição, autenticação. As APIs de checkout e reserva devem ser orquestradas por uma outra API ainda a definir, responsável pelo processo de roolback em caso de falhas.
</details>
<br/>

[:arrow_heading_up: voltar](#indice)

---

<a id="ferramentas"></a>
## :hammer: Ferramentas
As seguintes ferramentas foram usadas na construção do projeto:

- [Node.js](https://nodejs.org/en/)
- [Express](https://expressjs.com/en/)
- [TypeScript](https://www.typescriptlang.org/)
- [npm](https://www.npmjs.com/)
- [Nx](https://nx.dev/)
- [Docker](https://www.docker.com/)

[:arrow_heading_up: voltar](#indice)

---

<a id="boas-praticas"></a>
## :clap: Boas Práticas
Seguindo boas práticas de desenvolvimento:
- [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html)
- [keep a changelog](https://keepachangelog.com/en/1.0.0/)
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [Mermaid Diagrams](https://mermaid.js.org)
- [Monorepo](https://monorepo.tools/)
- [Architecture decision record (ADR)](https://github.com/joelparkerhenderson/architecture-decision-record)

[:arrow_heading_up: voltar](#indice)

---
<a id="desenvolvedores"></a>
## :nerd_face: Para Desenvolvedores
Nada do que for discutido nessa seção deve atrapalhar o [correto funcionamento e instalação](#computer-instalação) do projeto em uma máquina com o docker-compose funcional

Durante o estudo/desenvolvimento, foram adotadas as ferramentas [Nx](https://nx.dev/) (que requer Nodejs em sua máquina) e seu [console no VScode](https://marketplace.visualstudio.com/items?itemName=nrwl.angular-console) para a gestão de Monorepos. Para uma experiência de desenvolvimento e validação técnica do repositório, [sugiro instalação do ambiente de gerenciamento](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm). Explicar o funcionamento do Nx não é o objetivo do presente documento (até mesmo porque também estou aprendendo), mas [encorajo a buscar esses dados](https://nx.dev/getting-started/intro) caso deseje. [Qualquer Monorepo pode se tornar um monorepo Nx](https://blog.nrwl.io/adding-nx-to-an-existing-monorepo-by-running-one-command-426fa519d943).

Tenha bons estudos :)
<!-- `npx nx dep-graph` é MARAVILHOSO -->
[:arrow_heading_up: voltar](#indice)

---

<a id="versionamento"></a>
## :1234: Versões
Para obter mais informações, consulte o [Histórico de Versões](./CHANGELOG.md).

[:arrow_heading_up: voltar](#indice)

---

<a id="ia"></a>
### :robot: Uso de IA:

O cabeçalho desta página foi criado com a fonte [cinema-st](https://www.dafont.com/pt/cinema-st.font?text=CineTicket&psize=l) e o auxílio de inteligência artificial e um mínimo de 
retoque e construção no Gimp [<img src="./docs/images/icons/gimp.svg" width="30" height="30" title="Gimp" alt="Logo do Gimp" />](https://www.gimp.org/)


__Foram utilizados os seguintes prompts para sua criação no [Bing IA:](https://www.bing.com/images/create/)__


<details>
  <summary><b>Ingresso de cinema com rolo de filme</b></summary>
<i>"logotipo para um site de venda de ingressos de cinema estilo cartoon simplificado chamado cineticket, UM ingresso de cinema Azul com detalhes vermelhos rodeado por um negativo de rolo de filme de cinema com fundo branco"<b>(sic)</b></i>
</details>

<br/>


IA também é utilizada em minhas pesquisas e estudos como ferramenta de apoio; no entanto, __artes e desenvolvimento são, sobretudo, atividades criativas humanas.__

Contrate artistas para projetos comerciais ou mais elaborados e Aprenda Engenhosidade!

[:arrow_heading_up: voltar](#indice)
