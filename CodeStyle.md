# Orientações para desenvolvimento
## _Linguagem e termos_

A linguagem a ser adotada é o **inglês**, todas as variáveis, métodos, funções, nomes de arquivos, etc. devem usar terminologias em inglês, mantendo assim uma linguagem universal e sem misturas.

Exemplos:
``` Java
public ResponseEntity<ReleaseResponse> unrelease(
    @PathVariable final String accessGrantUuid,
    @PathVariable final String sessionId
) {
```
``` Java
public enum LoginStatus {
   	IN_PRODUCT, 
	IN_PLATFORM, 
	AVAILABLE;
}
```

## _Formatação padrão (.editorconfig)_

Em vista de manter todos os arquivos com mesmo padrão, seja visual, _charset_ ou de sistema. Fica definido as seguintes normativas:

- charset em `utf-8`
- Identação com tamanha de 4 espaços
- Edentação usando espaços (diferentes editores e ate mesmo o terminal, podem ter tamanhos diferentes para o `tab` ignorando um arquivo de regras inclusive; com espaço isso não ocorre).
- Termino de linha usando a padrão linux `LF` (os servidores são em linux)

Arquivo padrão do `.editorconfig` (recomenda-se que a IDE usada tenha suporte):
``` markdown
root = true

[*]
charset = utf-8
end_of_line = lf
indent_size = 4
indent_style = space
insert_final_newline = true
trim_trailing_whitespace = true

[*.md]
trim_trailing_whitespace = false
```

## _Legibilidade e clareza de informação_

- Estamos trabalhando com uma linguagem compilada, `Java`.
- Estamos usando transpiladores no front `grunt`, ou framework com build `angular`, `react`.

Com base nestes dois preceitos, recomenda-se clareza na definição de variáveis, classes, métodos, funções, etc. já que no fim estes são convertidos pelo motor de build e não terão grande impacto na performance.
Evite colocar nomes **subjetivos** ou **sem significado**, assim como **sigla**s que possam ter duplo sentido.

Exemplo de problemas:
``` Javascript
/* Não fica claro que componente é esse */
class NewComponect extends React.Component<Props, States>{
```
``` Typescript
/* Estas propriedades são do que? */
interface Props {
    name: string;
    age: string;
    permissions: Permission[];
}
```
``` Java
// Act = account, action, activity 
public void createNewActToUser(User user){
```

## _Estilo de codigo_

- Em vista de aumentar a legibilidade do código.

Métodos que possuam múltiplos parâmetros, devem quebrar cada parâmetro em uma linha com tabulação simples.
``` Java
private void validateUserRoleCreationByApiUser (
	Long apiUserId,
	Integer productId,
	UserRoleEntity userRoleToBeCreated
) {
```
``` Java
@PutMapping("/user")
public User updateUserInAdministrativeArea(
    @RequestHeader(name="X-APOLO-USER-ID") Long userLoggedId,
    @RequestBody final User user
) {
    return userService.updateUserInAdministrativeArea(userLoggedId, user);
}
```
Assim como para `tags` com múltiplas propriedades.
``` Html
<a
    id="button-conectar-cadastro"
    href="#/register"
    type="button"
    class="btn btn-default-americanas btn-block"
    ng-bind="components.get('text-btn-cadastro').value"
></a>
<input
    id="password"
    name="password"
    ng-model="auth.password"
    type="password"
    class="form-control input-md"
    placeholder="{{components.get('text-senha').value}}"
    required
/>
```
Na mesma linha de raciocínio chamadas em _"chain"_ devem ser quebradas em multiplas linhas
``` Java
@Bean
public Docket api() {
	return new Docket(DocumentationType.SWAGGER_2)
		.select()
		.apis(RequestHandlerSelectors.basePackage("br.com.mobicare.apolo"))
		.paths(PathSelectors.any()).build()
		.apiInfo(apiInfo());
}
```
A palavras reservadas `True`, `False`, `Null`, devem ser escritas em minusculo.
``` Java
true
false
null
```

Contantes devem ser escritas com todas as letras em maiúsculo, separadas por underline "_"
``` Java
PROJECT_VERSION = '0.07';
DAY_OF_THE_WEEK = 7;
API_URL = 'https://...';
```
