<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# FORGOT PASSWORD VIEW CONTROLLER
É a classe reponsavel por conectar a view com a viewModel que contem a regra de negocio.
  

  
## Propriedades:
```swift
private var viewModel: ForgotPasswordViewModelProtocol
    - intancia da viewModel para ter acesso aos seus metodos, providos pelo protocolo

let customView: ForgotPasswordView ...
    - É uma constante interna porque ela precisara ser acessada na hora do teste unitario 
    - View customizada para manter as reponsabilidades o mais separadas possivel
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

  
  
## INICIALIZADOR:
```swift
init(viewModel: ForgotPasswordViewModelProtocol) { ... }
    - Inicializa a viewModel, criando uma depencia testavel pelo protocolo
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>



## CICLOS DA VIEW UTILIZADOS:
```swift
... func loadView() {...}
    - Usado para settar a view padrao da controller como sendo a customView

... func viewDidLoad() {...}
    - Usado para chamar o metodo que setta os delegates nescessarios

... func viewDidDisappear(_ animated: Bool) {...}
    - usado para chamar o metodo `viewDidDisapearHandle` da viewModel, sera nescessario para desalocar quando a tela sumir.
```



## METODOS:
```swift
private func configureDelegates()
    - Configura o binding entre controller e a viewModel (viewDelegate)
```


  
## EXTENSÕES PARA IMPLEMENTAÇOES:
### ForgotPasswordViewController: ForgotPasswordViewModelToController {...}
```swift
//Ate o momento nao faz nada ...
```
</br>
  
### ForgotPasswordViewController: RegistrationViewModelToViewDelegate {...}
Contem as notificaçoes enviadas da view
```swift
func emailToRecoveryAccountWasChanged() {...}

func recovetyPasswordButtonHandleTapped(_ loader: ANPrimaryButtonHideDelagate) {...}
    - Esconde o loader
    - chama o metodo `recoveryButtonhandle` da viewModel
```
 </br>
  
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
