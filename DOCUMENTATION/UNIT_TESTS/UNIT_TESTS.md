<a name="top"><a/>
<p align="left"><a href="https://github.com/PaoloProdossimoLopes/repository-template/blob/main/DOCUMENTATION/README.md">◀️ BACK TO DOCUMENTATION</a></p>
    

# 📊 TESTES UNITARIOS
Implementar testes unitarios é uma forma de manter uma certa qualidade de codigo. O Teste nao deixa seu app livre de bugs, porem garante que nos cenarios que foram esperados as coisas estao certas, alem disso nao precisa ficar se preocupando com a cobertura de 100% isso é algo ideal em que na maioria dos casos nao é aplicavel, uma boa margem seria algo entre 70-80%, e nem todas as classes precisam ser testadas, por exemplo, nessa arquitetura adotada idealmente seria a viewModel, view e controller, algo que é valido tambem seria testar as classes de utils/helpers/extensions, porque como elas serao usadas de maneira vasta no codigo caso tenha ocorrido alguma mudança indesejada irá acarretar em muitos bugs.

## TESTES:

### Login
[LoginViewTest]() <br/>
[LoginViewModel]() <br/>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

### Register
[RegisterViewTest]() <br/>
[RegisterViewModel]() <br/>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

### Recovery
[RecoveryViewTest]() <br/>
[RecoveryViewModel]() <br/>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

### Extensions
[String+ExtenionsTest]() <br/>
[String+ExtenionsTest]() <br/>
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>

## DICAS
Recomento tambem nao usar uma dependencia para fazer testes unitarios e sim usar a padrao do iOS XCTest, ela ja é bem madura e possui muitos casos de XCTAssert. Outra recomendaçao seria criar nome bem descritiveis usado o seguinte modelo:

func test_GIVEN_WHEN_THEN() { }

Example:

```sh
func test_GivenPositiveBalance_WhenViewDidLoad_ThenBalanceSectionValueColorShouldBeGreen() {

    //GIVEN
    let model = AccountModel(balance: 200.0)
    let viewModel = AccountViewModel(model: model)
    let controller = AccountViewController(viewModel: viewModel)

    //WHEN
    let _ = controller.view //This step start view life cycle

   
    //THEN
    XCTAssertTrue(controller.AView.balanceValue.textColor, .balanceGreen)
}

```
<p align="right"><a href="#top">🔼 BACK TO THE TOP</a></p>
