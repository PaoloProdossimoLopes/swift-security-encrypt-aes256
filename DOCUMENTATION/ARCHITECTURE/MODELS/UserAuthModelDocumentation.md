<a name="#top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/ARCHITECTURE/ARCHITECTURE.md">◀️ BACK TO ARCHITECTURE</a></p>
  
  

# USER AUTH MODEL
Model obtida aparti do reponse da api da classe LoginService
  
  
  
## CARACTERISTICAS:
  
#### Tipo:
  - [ ] Class 
  - [X] Struct

#### Herança:
  - [ ] Class: 
  - [X] Protocols:
    - Codable
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
## PROPRIEDADES:
<pre>
private let response: UserAuthModelResponse
    |-* Propriedade base para manipulaçao nessa model que sera usada na LoginViewModel
    
var name: String { ... }
    |-* Retorna o nome do usuari
    
var userName: String { ... }
    |-* Retorna no nome customizado do usuario acompanhado da formataçao adequada (acompanhado do @)
    |-* Exemplo: @PROLS
...
</pre>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## INICIALIZADOR:
<pre>
init(response: UserAuthResponseModel) { ... }
</pre>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
  
  
## METODOS:
<pre>
private func createUsernameFormatation() -> String { ... }
    |-* Metodo reponsavel form concatenar o username para gera-lo
....
</pre>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
  
