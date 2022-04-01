<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# LOGIN VIEW CONTROLLER
É a classe reponsavel por conectar a view com a viewModel que contem a regra de negocio.
  

  
## Propriedades:
```swift
private var viewModel: LoginViewModelProtocol
    - intancia da viewModel para ter acesso aos seus metodos, providos pelo protocolo

let customView: LoginView ...
    - É uma constante interna porque ela precisara ser acessada na hora do teste unitario 
    - View customizada para manter as reponsabilidades o mais separadas possivel
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## INICIALIZADOR:
```swift
init(viewModel: LoginViewModelProtocol) { ... }
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
### LoginViewController: LoginViewModelToViewDelegate {...}
Essa extensao é reponsavel por conectar a viewModel com a controller
```swift

```
</br>
  
### LoginViewController: LoginViewDelegate {...}
Essa extensao é reponsavel por conectar a view customizada com a controller
```swift
func textFieldUpdatedHandle()
    - Chama o metodo `textFieldUpdatedHandle` da viewModel

func enterButtonHandleTapped(_ loader: ANPrimaryButtonHideDelagate)
    - Chama o metodo `enterButtonHandleTapped` da viewModel

func forgotPasswordButtonHandleTapped()
    - Chama o metodo `forgotPasswordHandleTapped` da viewModel

func registerButtonHandleTapped(_ sender: UIButton)
    - Chama o metodo `registerButtonHandleTapped` da viewModel
```
 </br>
  
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
