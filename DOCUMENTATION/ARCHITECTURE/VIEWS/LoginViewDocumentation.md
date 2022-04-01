<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# LOGIN VIEW
É a tela onde o usuario deve poder colocar valores nos textfields e clicar nos botoes.
  
 
  
## PROTOCOLOS:
#### LoginViewDelegate - AnyObject
Notifica a controller caso os textfields sejam alterados ou os botoes sejam clicados.
<pre>
func textFieldUpdatedHandle()
    - Atualiza a cada Ativaçao do delegate do textField

func enterButtonHandleTapped(_ loader:)
    - Ativa ao clicar no botao de login

func forgotPasswordButtonHandleTapped()
    - Ativa ao clicar na label

func registerButtonHandleTapped(_ sender:)
    - Ativa ao Clicar no botao de registro
</pre>

<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## DEPENDENCIAS:
<pre>
private(set) weak var delegate: LoginViewDelegate?
    - Delegate para as actions
    - Referencia fraca
</pre>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## UI Components:
<pre>
... var emailTF: ANPrimaryTextField
    - Campo para preencher com o Email

... var passwordTF: ANPrimaryTextField
    - Campo para preencher com a senha

... var textFieldsStacks: UIStackView 
    - Contem os campos de senha e email, esqueceu a senha e botao
     de login

... var enterButton: ANPrimaryButton
    - Botao de logar no app e ser direcionado para a home

... var captionMessageWithButton: UIStackView
    - Esse componente comporta os textos para registrar

... var forgotYourPasswordButton: UILabel
    - Esse label tem uma açao vinculada para direcionar a 
    outra tela

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
@objc private func forgotPasswordButtonWasTapped() { ... }
    - Captura o clique na label que deve levar a tela 
    de esqueceu a senha.
    
@objc private func registerButtonWasTapped(_ sender: UIButton)
    - Captura o clique no botao que deve levar a tela de registro.
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
