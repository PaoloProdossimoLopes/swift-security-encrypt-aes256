<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# REGISTRATION COORDINATOR
É a classe responsavel por conduzir o fluxo da aplicaçao para a cena de login e esqueceu a senha.



## Protocolos:
### RegistrationCoordinatorDelegate: AnyObject  {...}
Responsavel por delegar açoes ao coordinator do LoginCoordinator
```swift
func dealocate()
    - Metodo que avisa que deve ser desalocado por quem instancia/ chama ele
```
</br>


## Propriedades:
```swift
weak var delegate: RegistrationCoordinatorDelegate?
    
private let service: RegistrationServiceProtocol
    - Instancia a service e que sera apssada como dependencia da viewModel
    
private lazy var viewModel: RegistrationViewModel 
    - Instancia a viewModel, passando como dependecia a service e ja settando o coordinatorDelegate dela como sendo self

private lazy var controller: RegistrationViewController
    - Instacia a RegistrationViewController passando como dependencia a viewModel

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
  
### RegistrationCoordinator: RegistrationViewModelToCoordinatorDelegate {...}
```swift
func dismissRegistration()
    - Responsavel por remover a registrationController usando o router que executara um pop (ja que é a segunda tela)
    - acionara o metodod `dealocate` do delegate para desaloca-la da memoria
```
</br>
  
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
