<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# FORGOT PASSWORD VIEW MODEL
É a classe reponsavel por cuidar das regras de negocio do aplicativo e tomada de decisoes nas interações.



## Protocolos:
### ForgotPasswordViewModelToController: AnyObject  {...}
Responsavel por fazer o binding entre a controller para que notifique a view.
```swift
```
</br>

### ForgotPasswordViewModelToCoordinator: AnyObject {...}
Responsavel por notificar o coordinator sobre a tomada de decisao
```swift
func closeForgotPassword(_ controller: ForgotPasswordViewController, shouldDismiss: Bool)
    - Aciona para avisar ao coordinator que o deve fechar a tela.
```
</br>

### ForgotPasswordViewModelProtocol {...}
Protocolo criado para encapsulamento da classe na controller. Por conta disso cada componente dele será abordado na sua respectiva seçao da classe.


## Propriedades:
```swift
weak var viewDelegate: ForgotPasswordViewModelToViewDelegate?
    - Essa propriedade é usada para acessar os metodos que serao implementados pela Controller
    - Referencia fraca para evitar vazamento de memoria

weak var coordinatorDelegate: ForgotPasswordViewModelToCoordinatorDelegate?
    - Essa propriedade é usada para acessar os metodos que serao implementados pelo Coordinator
    - Referencia fraca para evitar vazamento de memoria

private let service: ForgotPasswordServiceProtocol
    - Essa propriedade é usada para acessar os metodos do service para chamar as apis 

```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

  
  
## INICIALIZADOR:
```swift
init(service: ForgotPasswordServiceProtocol) { ... }
    - Inicializa a service, responsavel por chamar as APIs cabiveis
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>



## METODOS:
```swift
func registerHandleTapped(_ viewController: ForgotPasswordViewController, loader: ANPrimaryButtonHideDelagate)
    - Se comunica na service
    - Chama a uma funcao da coorindatorDelegate chamda `closeForgotPassword`
    - caso sucesso, aciona o delegate
    - caso falha , apresenta popUp

func alreadyHaveaccountHandleTapped(_ viewController: RegistrationViewController)
    - Aciona o coordinator chamado `closeForgotPassword` para voltar a tela de login
```
  
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
