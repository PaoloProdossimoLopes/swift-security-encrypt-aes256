<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# FORGOT PASSWORD VIEW
É a tela onde o usuario deve poder colocar valores nos textfields e clicar nos botoes.
  
 
  
## PROTOCOLOS:
#### ForgotPasswordViewDelegate - AnyObject
Notifica a controller caso os textfields sejam alterados ou os botoes sejam clicados.
```swift
func emailToRecoveryAccountWasChanged()
    - Reponsavel por notificar a controller de que o emailToRecoveryAccountTextField foi acionado pelo delegate.
    
func recovetyPasswordButtonHandleTapped(_ loader: ANPrimaryButtonHideDelagate)
    - Notifica a controller que o botao de recuperaçao de conta foi clicado.
    
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## DEPENDENCIAS:
```swift
private(set) weak var delegate: ForgotPasswordViewDelegate?
    - Delegate para o binding entre a view e controller
    - Referencia fraca
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## UI Components:
```swift
... var emailToRecoveryAccountTextField: ANPrimaryTextField
    - Textfield para a cadatrar o nome do usuario

... var informationLabel: UILabel
    - Textfield para a cadatrar o nome do usuario

... var recoveryPasswordButton: ANPrimaryButton
    - Textfield para a cadatrar o email do usuario
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## INICIALIZADOR:
```swift
init(_ delegate: ForgotPasswordViewDelegate?) { ... }
    - Inicializa o delegate
    - chama o commonInit do protocolo ANConfiguratorLayout
```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  

  
## EXTENSÕES PARA IMPLEMENTAÇOES:
### ForgotPasswordView: ANViewLayoutConfigurator {...}
Essa extensao contem os metodos para configurar o layout
```swift
func commonInit() { ... }
    - Utilidade: Centralizar as funcoes em um starter para ser chamado no init
    
func configureViewHierarchy() { ... }
    - Utilidade: Centralizar os ajustes de hierarquia de view
    
func configureConstraints() { ... }
    - Utilidade: Centralizar os ajustes de constraints
```
</br>
  
### ForgotPasswordView: ANPrimaryTextFieldDelegate {...}
Tem os delegates relacionados ao componente customizado do textfield

```swift
func notifyWhenTextFieldWasChanged() {...}
  - Notifica quando o TextField é modificado
  - Valida o estado do botao para ver se deve ser habilitado ou nao
```
</br>
  
### ForgotPasswordView: ANPrimaryButtonDelegate {...}
Contem o delegate do botao customizado para notificar quando for acionado
```swift
func handleButtonTapped(_ loader: ANPrimaryButtonHideDelagate) {...}
  - Notifica quando o botao é clicado.
```
</br>
  
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
