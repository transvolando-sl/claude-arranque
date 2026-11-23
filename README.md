# Arranque del Claude Code de Transvolando

Instrucciones para **Claude Code**. La persona te ha pedido que configures su Claude. Háblale en español de España, de
tú, con frases cortas, y ve de un paso en uno. Lo que puedas hacer desde Claude Code, hazlo tú; lo que no, dile
exactamente qué tocar y espera a que te diga «hecho». **Nunca** pidas, escribas ni repitas contraseñas, códigos ni llaves.

## 1. Su sector
Pregúntale de qué sector es y usa este nombre corto: `trafico` (Gestión de tráfico) o `administracion` (Administración
y documentación). Si es de otro sector, dile que todavía no hay paquete y que avise a Soporte y Tecnología.

## 2. Git y GitHub CLI
Comprueba `git --version` y `gh --version`. Si falta alguno, instálalo tú:
```
winget install --id Git.Git -e
winget install --id GitHub.cli -e
```
Avísale de que Windows le pedirá permiso y tiene que aceptarlo. Si después no encuentra los comandos, que cierre y vuelva a abrir Claude.

## 3. Entrar en GitHub (lo hace la persona)
Comprueba `gh auth status`. Si no hay sesión, dile:
1. Abre PowerShell.
2. Escribe `gh auth login` y elige: GitHub.com › HTTPS › Login with a web browser.
3. Copia el código que aparece, pégalo en la página que se abre y entra con tu cuenta de GitHub.
4. Escribe `gh auth setup-git`.
Si no tiene cuenta de GitHub o no ha aceptado la invitación de la organización, que avise a Soporte y Tecnología.

## 4. Instalar los paquetes (lo haces tú)
```
claude plugin marketplace add transvolando-sl/claude-comun
claude plugin marketplace add transvolando-sl/claude-<sector>
claude plugin install transvolando-comun@transvolando-comun
claude plugin install transvolando-<sector>@transvolando-<sector>
```
Si da error de acceso, falta la invitación de GitHub: que avise a Soporte y Tecnología.

## 5. Seguir
Dile que cierre y vuelva a abrir Claude y que te escriba **«sigue configurando»**. A partir de ahí, la habilidad
`configurar-mi-claude` del paquete se ocupa del resto: actualizaciones, conectores, firma y una prueba.
