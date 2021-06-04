# Teste de unidade

- Frameworks
- Nomeclaturas
- Ferramentas
- Escrita de testes
- Features do framework de teste
- Execução no VS, VSCode, CLI
- Mock
- AutoMock
- Fixture
- Geração de dados
- Fluent Assertions


##Frameworks para teste de unidade

- MSTest
    - Microsoft/Comunidade/Preferência
- NUnit
    - Portabilidade do JUnit(Java)
- XUnit
    - Mais novo baseado no NUnit

##xUnit.net

- Escrito pelos criadores do NUnit
- Compatível com Visual Studio
- Utilizado pelo time de desenvolvimento do .NET Core e ASP.NET

Instalação do framework
`Install-Package xunit`
Instalação para reconhecimento do Visual Studio
`Install-Package xunit.runner.visualstudio`

##Padrões e Nomeclaturas

###AAA - Arrange, Act, Assert

- Arange
    - Gerar objeto no ponto certo para atuar
- Act
    - Ação que será testada
- Assert
    - Validar os resultados gerados conferem com a intenção dos testes

Exemplo 
```cs
[TestMethod]
public void Withdraw_ValidAmount_ChangesBalance()
{
    // arrange
    double currentBalance = 10.0;
    double withdrawal = 1.0;
    double expected = 9.0;
    var account = new CheckingAccount("JohnDoe", currentBalance);

    // act
    account.Withdraw(withdrawal);

    // assert
    Assert.AreEqual(expected, account.Balance);
}
```

##Padrão de nomemclatura

ObjetoEmTeste_MetodoComportamentoEmTeste_ComportamentoEsperado

Exemplo: **Pedido_AdicionarPedidoItem_DeveIncrimentarUnidadesSeItemJaExistente**

MetodoEmTeste_EstadoEmTeste_ComportamentoEsperado
Exemplo: **AdicionarPedidoItem_ItemExistenteCarrinho_DeveIncrementarUnidadesDoItem**

##Mock

Objetos Mock são simulações de comportamento de objetos reais de forma controlada.
Mock pode ser criado dinamicamente atráves de um framework de Mock.

###Moq

- Realize Mock com facilidade
- Compatível com Visual Studio
- Utilizado pelo time de desenvolvimento do .NET Core e ASP.NET

Instalação do framework

`Install-Package Moq`
