<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# REGISTRATION VIEW
É a tela onde o usuario deve poder colocar valores nos textfields e clicar nos botoes.
  
 
  
## PROTOCOLOS:
#### RegistrationViewDelegate - AnyObject
Notifica a controller caso os textfields sejam alterados ou os botoes sejam clicados.
<pre>
func registerButtonHandleTapped(_ loader: ANPrimaryButtonHideDelagate)
    - Ativo quando o o delegate do botao é acionado

func alreadyHaveAccountHandleTapped()
    - Ativo pelo selector reponsavel pelo botao de voltar a tela de login
</pre>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## DEPENDENCIAS:
<pre>
private(set) weak var delegate: RegistrationViewDelegate?
    - Delegate para o binding entre a view e controller
    - Referencia fraca
</pre>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## UI Components:
<pre>
... var nameTF: ANPrimaryTextField
    - Textfield para a cadatrar o nome do usuario

... var usernameTF: ANPrimaryTextField
    - Textfield para a cadatrar o nome do usuario

... var emailTF: ANPrimaryTextField
    - Textfield para a cadatrar o email do usuario

... var passwordTF: ANPrimaryButton
    - Textfield para a cadatrar a senha do usuario

... var registrationButton: ANPrimaryTextField
    - Botao para registrar o usuario

... var mainStackView: UIStackView
    - Stack que contem os textfield de nome, username, email, password e o botao de registro

... var captionMessageWithButton: UIStackView
    - Satck para a construçao do texto de dois estilos com botao de voltar para a loginView

</pre>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## INICIALIZADOR:
<pre>
override init(frame: CGRect){ ... }
    - Apenas para conter o comminInit do 
    protocolo ANConfiguratorLayout
</pre>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
<!--
## METODOS:
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
-->
  
  
## SELECTORS:
  
<pre>
@objc private func alreadyHaveAccotunButton() { ... }
    - Captura o clique no botao dizendo que 
</pre>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  

  
## EXTENSÕES PARA IMPLEMENTAÇOES:

### LoginView: ANViewLayoutConfigurator {...}
Essa extensao contem os metodos para configurar o layout
<pre>
func commonInit() { ... }
    - Utilidade: Centralizar as funcoes em um starter para ser chamado no init
    
func configureViewHierarchy() { ... }
    - Utilidade: Centralizar os ajustes de hierarquia de view
    
func configureConstraints() { ... }
    - Utilidade: Centralizar os ajustes de constraints
</pre></br>
  
### LoginView: ANPrimaryTextFieldDelegate {...}
Tem os delegates relacionados ao componente customizado do textfield
<pre>
func notifyWhenTextFieldWasChanged() {...}
  - Notifica quando o TextField é modificado
</pre> </br>
  
### LoginView: ANPrimaryButtonDelegate {...}
Contem o delegate do botao customizado para notificar quando for acionado
<pre>
func handleButtonTapped(_ loader: ANPrimaryButtonHideDelagate) {...}
  - Notifica quando o botao é clicado.
</pre></br>
  
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
