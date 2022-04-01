<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# LOGIN VIEW MODEL
É a classe reponsavel por cuidar das regras de negocio do aplicativo e tomada de decisoes nas interações.



## Protocolos:
### LoginViewModelToViewDelegate: AnyObject  {...}
Responsavel por fazer o binding entre a controller para que notifique a view.
```swift
//Ate o momento nao faz nada ...
```
</br>

### LoginViewModelToCoordinatorDelegate: AnyObject {...}
Responsavel por notificar o coordinator sobre a tomada de decisao
```swift
func goToHome(_ controller: LoginViewController)
    - Notificará o coordinator para levar o usuario ate a Home

func goToForgotPassword(_ controller: LoginViewController)
    - Notificara o coordinator de levar o usuario ate a tela de recuperar conta

func goToRegister(_ controller: LoginViewController)
    - Notificara ao coordinator para levar a tela de registro
```
</br>

### LoginViewModelProtocol {...}
Protocolo criado para encapsulamento da classe na controller. Por conta disso cada componente dele será abordado na sua respectiva seçao da classe.


## Propriedades:
```swift
weak var viewDelegate: LoginViewModelToViewDelegate?
    - Essa propriedade é usada para acessar os metodos que serao implementados pela Controller

weak var coordinatorDelegate: LoginViewModelToCoordinatorDelegate?
    - Essa propriedade é usada para acessar os metodos que serao implementados pelo Coordinator

private let service: LoginServiceProtocol
    - Essa propriedade é usada para acessar os metodos do service para chamar as apis 

```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

  
  
## INICIALIZADOR:
```swift
init(_ coordinatorDelegate: LoginViewModelToCoordinatorDelegate, service: LoginServiceProtocol) { ... }
    - Inicializa o delegate do coordinator para delegar a responsabilidade de navegaçao a ele
    - Inicializa a service, responsavel por chamar as APIs cabiveis
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>



## METODOS:
```swift
func textFieldUpdatedHandle()
    - funcao para tratar a mudança do textField
    - Até o momento nao faz nada

func enterButtonHandleTapped(_ controller: LoginViewController, loader: ANPrimaryButtonHideDelagate)
    - Funcao da viewModel para tratar o clique no botao de Logar.
    - chamara a o metodo cooridnatorDelegate chamado `goToHome`, implementado pelo LoginCoordinator

func forgotPasswordHandleTapped(_ controller: LoginViewController)
    - Funcao da viewModel que cuidara da logica do botao que leva ao esqueceu a senha
    - chamara a o metodo cooridnatorDelegate chamado `goToForgotPassword`, implementado pelo LoginCoordinator

func registerButtonHandleTapped(_ controller: LoginViewController)
    - Funcao da viewModel que cuidara da logica do botao que leva ao registro
    - chamara a o metodo cooridnatorDelegate chamado `goToRegister`, implementado pelo LoginCoordinator
```
  
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
