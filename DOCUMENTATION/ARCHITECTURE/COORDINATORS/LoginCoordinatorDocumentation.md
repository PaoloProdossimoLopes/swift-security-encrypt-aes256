<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# LOGIN COORDINATOR
É a classe responsavel por conduzir o fluxo da aplicaçao para a cena de login e esqueceu a senha.



## Protocolos:
### LoginCoordToModuleCoordDelegate: AnyObject  {...}
Responsavel por delegar açoes ao coordinator do modulo ANAuth
```swift
func goToHome(_ controller: LoginViewController)
    - Nofifica que o usuario quer/ deve ser direcionado para a home
```
</br>


## Propriedades:
```swift
weak var delegate: LoginCoordToModuleCoordDelegate?
    - Delegará as açoes ao cordinator do modulo
    
private var service: LoginServiceProtocol
    - Instanciará a service para ser passada como dependecia para a viewModel

private lazy var viewModel: LoginViewModel
    - Instanciara a viewModel, passado como dependencia (Abstrata) a service

private lazy var controller: LoginViewController
    - Instanciara a LoginViewController para ser chamada pela presenter

private var forgotPasswordCoordinator: ForgotPasswordCoordinator?
    - Instanciará quando nescessario o cooridnator da esqueceu a senha

private var registerCoordinator: RegistrationCoordinator?
    - Instanciará quando nescessario o coordinator da tela de registro

```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

  
  
## INICIALIZADOR:
- Nao esta sendo reescrito mas para contextualizar a documentaçao ele é:
```swift
ovveride init(router: Router) { ... }
    - Sera nescessario passar alguns dos modelos de router prensentes na ANLIB, dependendo da nagegaçao
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>



## METODOS:
```swift
override func start() 
    - Chama a present
    
override func present(animated: Bool, onDismissed: Coordinator.onDismissedCallback?)
    - Por meio do router inicializado, sera usado o presenter dele para navegar a tela.
```


## EXTENSÕES PARA IMPLEMENTAÇOES:

### LoginCoordinator: LoginViewModelToCoordinatorDelegate {...}
```swift
func goToHome(_ controller: LoginViewController
    - Sera noficado que devera direcionar o usuario a home (avisando o coord pai)
    - Aciona o metodo `goToHome` do delegate (Pai)
    
func goToForgotPassword(_ controller: LoginViewController)
    - Sera noficado que devera direcionar o usuario a home (avisando o coord pai)
    - Instanciará o cooridnator da ForgotPassword
    
func goToRegister(_ controller: LoginViewController)
    - Sera noficado que devera direcionar o usuario a home (avisando o coord pai)
    - Instanciará o cooridnator da Register
```
</br>
  
### LoginCoordinator: ForgotPasswordCoordinatorDelegate {...}
Contem o delegate do botao customizado para notificar quando for acionado
```swift
func dismissMe()
    - Metodo usado quando a forgot password é fechada, usamos ele para desalocar da memoria a instancia do coordinator
```
</br>

### LoginCoordinator: RegistrationCoordinatorDelegate {...}
Contem o delegate do botao customizado para notificar quando for acionado
```swift
func dealocate() 
    - Metodo usado quando a Registration é fechada, usamos ele para desalocar da memoria a instancia do coordinator
```
</br>
  
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
