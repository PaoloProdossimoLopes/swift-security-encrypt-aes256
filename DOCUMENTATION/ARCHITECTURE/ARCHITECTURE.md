<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/README.md">◀️ BACK TO DOCUMENTATION</a></p>

# 🗂 ARQUITETURA
O APP CONSISTE EM MVVM-C (MODEL, VIEW/ CONTROLLER, VIEW MODEL, COORDINATOR) ESSA É A ESTRUTURA ESCOLHIDA POR SER BEM COMPATIVEL E OTIMIZADA PARA A ESTRATEGIA DE MODULARIZAÇÃO.

<br/>

## VIEWS
As Views sao reponsaveis por apresentar ao usuario os componentes visuiais e indentificar as interaçoes para notificar a repectiva controller vinculada a view.
### Views:
[LoginView](https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/VIEWS/LoginViewDocumentation.md) <br/>
[RegisterView](https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/VIEWS/RegistrationViewDocumentation.md) <br/>
[RecoveryView](https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/VIEWS/ForgotPasswordViewDocumentation.md.md) <br/>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

## CONTROLLERS
As Controllers sao reponsaveis por separar as reponsabilidades das views e das viewModels.
### Controllers:
[LoginViewController](https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/CONTROLLERS/LoginViewControllerDocumentation.md) <br/>
[RegisterViewController](https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/CONTROLLERS/RegistrationViewControllerDocumentation.md) <br/>
[RecoveryViewController](https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/CONTROLLERS/ForgotPasswordViewControllerDocumentation.md) <br/>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

## MODELS
As Models são os nossos modelos de dados que serao tranferidos entre scenas e usados para mudancas de informacoes, decodificaçao encodificaçao etc ...
### Models:
[UserAuthModel]() <br/>
[UserResponseModel]() <br/>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

## VIEWMODELS
As ViewModels sao responsaveis pelas tomadas de decisoes e tambem é quem contem as regras de negocio, comunicaçao com a service, manipulaçao das models ..., é importante resaltar que nao precisa ter apenas uma viewModel para cada cena, dependendo da complexidade e da quantidade de regras é valido criar mais de uma viewModels, para que a classe nao fique muito massiva.
### ViewModels:
[LoginViewModel](https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/VIEW_MODELS/LoginViewModeDocumentationl.md) <br/>
[RegisterViewModel](https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/VIEW_MODELS/RegistrationViewModelDocumentation.md) <br/>
[RecoveyViewModel](https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/VIEW_MODELS/ForgotPasswordViewModelDocumentation.md) <br/>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

## SERVICE
As Services sao responsaveis por fazer a comuniçacao com as APIs. O idela é criar uma service para cada api, ou scena, mas isso vai variar de desenvolvedor e nescessidade, recomendo ter isso bem alinhado para que o projeto mantenha um padrao.
### Services:
[LoginService]() <br/>
[RegisterService]() <br/>
[RecoveryService]() <br/>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

## COORDINATORS
Os cordinators sao os pontos chaves para a modularizao nessa arquitetura, isso pois com eles servem para separa a responsabilidade de exibiçao de telas (logica e modo de aprensentaçao) alem disso com eles é possivel deixar as cenas completamente idenpendente e podendo ser chamdas de qualquer ponto so app.
### Coordinators:
[ModuleAppCoordinator]() <br/>
[LoginCoordinator]() <br/>
[RegisterCoordinator]() <br/>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

**OBS:** O recovery nao tem coord proprio pq nesse exemplo ele so seria acessado via cena de login, por isso nao é nescessario ele ser completamente idependente.
