## Ex1
1. Pérdida de control de acceso
Descripción: Cuando un usuario sin privilegios puede acceder a contenidos para los que necesitaría un acceso privilegiado.
Impacto: Desde revelación de información que no debería conocerse a modificación indeseada de datos o eliminación de datos.
Medidas: Sanitización de entradas, implementación de accesos por rol o principios de mínimo privilegio necesario.
2. Fallas Criptográficas
Descripción: Todos aquellos fallos de ciberseguridad relacionados con el cifrado de datos.
Impacto: Revelación de secretos y posibilidad de descifrado de tráfico.
Medidas: Utilizar algoritmos aprobados por el FIPS-140, no incluir contraseñas o claves dentro del código o forzar el HTTPS.
3. Inyección
Descripción: Todas aquellas vulnerabilidades donde el usuario puede introducir parámetros no deseados en una página web, provocando consultas no deseadas a la base de datos o incluso la ejecución de comandos indeseados en el sistema operativo.
Impacto: Una vulnerabilidad de este estilo puede comprometer todo el servidor de la web.
Medidas: Sanitización de todos los inputs del usuario, ya sea a nivel de cookies, cabeceras HTTP, URL o parámetros del formulario. Además, se recomienda la introducción de herramientas SAST, DAST y IAST en las pipelines de desarrollo para su detección y prevención.
## Ex2
Ex1: jane' --
Ex2: '; DROP TABLE users--
Ex3: 'OR TRUE --
Ex4: 'OR TRUE limit 1 --
Ex5: '; SELECT username, password from users--
Ex6: '; SELECT salary AS username FROM staff WHERE firstname = 'Greta Maria'
Ex7: ' UNION SELECT name, email, salary, employed_since FROM staff --
Es poden evitar atacs d'injecció sql fent servir FromSqlInterpolated, FromSqlRaw amb paràmetres explícits o amb LINQ.
Font: https://snyk.io/blog/preventing-sql-injection-entity-framework/
## Ex3
Asumcions:
El pagament es realitza a través d'una passarel·la segura i els client no necessiten veure en cap moment les dades bancàries dels artistes. Així mateix, els artistes no necessiten veure les dades dels clients, ja que el sistema farà la comanda i l'enviament de part seva.
a:
Clients - modificar contrasenya, veure i modificar Nom, Cognoms, DNI, adreça, i telèfon propis, veure foto, descripció i preu de l'obra i llegir i escriure resenyes
Artista - modificar contrasenya, veure i modificar Nom, Cognoms, DNI, adreça, dades bancàries i telèfon propis, veure i modificar foto, descripció i preu de l'obra i llegir resenyes
Account Manager - Veure dades dels artistes

b:
12 caràcters. Inclou majúscules, minúscules, números i caràcters especials. No son necessàries polítiques diferents.

c:
S'hauria d'encriptar tota la informació excepte les resenyes.

## Ex4
Definició: L'autenticació basada en tokens és un mètode de control d'accés en què un sistema genera un codi d'autenticació que s'utilitza per identificar un usuari en lloc d'utilitzar noms d'usuari i contrasenyes a cada petició. El token actua com una prova que l'usuari ja ha estat autenticat i autoritzat per accedir a determinades funcionalitats.
Tipus: JWT (JSON Web Tokens), OAuth, Bearer Tokens o SAML (Security Assertion Markup Language), entre d'altres.
Funcionalitat: Primer l'usuari es registre, i si el registre es vàlid es genera una token. Després, aquest token s'utilitza per verificar l'usuari a la capçalera HTTP, després es verifica el token i per últim el servidor envia la resposta a l'usuari.
Llibreries: ASP.NET Core Identity, System.IdentityModel.Tokens.Jwt i Microsoft.AspNetCore.Authentication.JwtBearer, entre d'altres.

## Ex6 (bibliografia):
No he necessitat consultar res, ja que algú que treballa en ciberseguretat m'ha ajudat a fer el treball.
