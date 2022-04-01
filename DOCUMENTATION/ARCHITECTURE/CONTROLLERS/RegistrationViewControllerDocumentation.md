<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# REGISTRATION VIEW CONTROLLER
É a classe reponsavel por conectar a view com a viewModel que contem a regra de negocio.
  

  
## Propriedades:
```swift
private var viewModel: RegistrationViewModelProtocol
    - intancia da viewModel para ter acesso aos seus metodos, providos pelo protocolo

let customView: RegistrationView ...
    - É uma constante interna porque ela precisara ser acessada na hora do teste unitario 
    - View customizada para manter as reponsabilidades o mais separadas possivel
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

  
  
## INICIALIZADOR:
```swift
init(viewModel: RegistrationViewModelProtocol) { ... }
    - Inicializa a viewModel, criando uma depencia testavel pelo protocolo
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>



## CICLOS DA VIEW UTILIZADOS:
```swift
... func loadView() {...}
    - Usado para settar a view padrao da controller como sendo a customView

... func viewDidLoad() {...}
    - Usado para chamar o metodo que setta os delegates nescessarios
```



## METODOS:
```swift
private func configureDelegates()
    - Configura o binding entre controller e a viewModel (viewDelegate)
    - Configura o binding entre a customView e a controller 
```


  
## EXTENSÕES PARA IMPLEMENTAÇOES:
### RegistrationViewController: RegistrationViewDelegate {...}
Essa extensao contem os metodos para configurar o layout
```swift
func registerButtonHandleTapped(_ loader: ANPrimaryButtonHideDelagate) {...}
    - Chama o metodo `registerHandleTapped` da viewModel

func alreadyHaveAccountHandleTapped() {...}
    - Chama o metodo `alreadyHaveaccountHandleTapped` da viewModel
```
</br>
  
### RegistrationViewController: RegistrationViewModelToViewDelegate {...}
Tem os delegates relacionados ao componente customizado do textfield
```swift
func updateView()
    - Metodo ativado quando a viewModel faz algo que nescessite que a view seja atualizada.
```
 </br>
  
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
