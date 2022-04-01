<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# FORGOT PASSWORD COORDINATOR
É a classe responsavel por conduzir o fluxo da aplicaçao para a cena de login e esqueceu a senha.



## Protocolos:
### ForgotPasswordCoordinatorDelegate: AnyObject  {...}
Responsavel por delegar açoes ao coordinator do LoginCoordinator
```swift
func dismissMe()
    - Metodo que avisa que deve ser desalocado por quem instancia/ chama ele
```
</br>


## Propriedades:
```swift
private weak var delegate: ForgotPasswordCoordinatorDelegate?
    - Responsavel por delegar a açao a quem o instanciar
    
private var service: ForgotPasswordServiceProtocol
    - Instancia a service e que sera apssada como dependencia da viewModel
    
private lazy var viewModel: ForgotPasswordViewModel
    - Instancia a viewModel, passando como dependecia a service e ja settando o coordinatorDelegate dela como sendo self

private lazy var controller: ForgotPasswordViewController
    - Instacia a ForgotPasswordViewController passando como dependencia a viewModel

```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

  
  
## INICIALIZADOR:
- Nao esta sendo reescrito mas para contextualizar a documentaçao ele é:
```swift
init(_ delegate: ForgotPasswordCoordinatorDelegate, router: Router) { ... }
    - Sera nescessario passar alguns dos modelos de router prensentes na ANLIB, dependendo da nagegaçao
    - Sera nescessario quem implementa-lo, passar-se commo reponsavel para as suas delegaçoes.
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>



## METODOS:
```swift
override func start() 
    - Chama a present
    
override func present(animated: Bool, onDismissed: Coordinator.onDismissedCallback?)
    - Por meio do router inicializado, sera usado o presenter dele para navegar a tela.

override func dismiss(animated: Bool, onDismissed: (Coordinator.onDismissedCallback?) = nil)
    - Responsavel por usar o router para remover o a tela
```


## EXTENSÕES PARA IMPLEMENTAÇOES:
  
### ForgotPasswordCoordinator: ForgotPasswordViewModelToCoordinator {...}
```swift
func closeForgotPassword(_ controller: ForgotPasswordViewController, shouldDismiss: Bool) 
    - Sera responsavel por remover a ForgotPassword de vista ( caso o usuario nao tenha tirado view swipe )
    - Aciona o `dismissMe` do delegate para desaloca-lo da memoria.
```
</br>
  
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
