# Azure Active Directory Summary
 Resumen: Azure Active Directory Puntos Importantes para su implementaci贸n


##### 1. Terminolog铆a Clave de AD - 馃槂

**- Identidad:** algo que se puede autenticar. Ej: Para un usuario final puede ser user ID o correo electr贸nico y contrase帽a. Para una app puede ser app ID o certificado que se utilice para aplicar la autenticaci贸n

**- Cuenta:** Tiene datos asociados a la identidad, una vez que te autenticas puedes tener acceso a nombre de usuario, perfil, a que rol pertenece, diferente informaci贸n asociada a esa identidad.



> __No existe cuenta sin identidad. Para tener una cuenta se debe tener una identidad.__



**- Cuenta de Azure AD:** Se crea al ocupar un servicio en la nube como portal de Azure, o servicios de Microsoft 365. De esta manera tu identidad (correo electr贸nico o tu user ID) est谩 registrada en un directorio de Azure AD, as铆 mismo se puede utilizar esta cuenta para hacer uso de correo electr贸nico, y servicios internos y externos.

**- Administrador de cuenta:** Asociado al administrador que puede realizar o hacer gesti贸n de facturaci贸n.

**- Administrador de servicios:** tiene acceso a todos los servicios de suscripci贸n de Azure, puede tener control completo a todos los servicios que est谩n desplegados en la suscripci贸n.

**- Propietario:** Tiene control m谩s detallado sobre alg煤n recurso como app web. Es importante dar los accesos pertinentes con quien se comparten los accesos.



> __Evitar que el usuario pueda eliminar los recursos que creamos.__


> __Dar al usuario el acceso m铆nimo requerido para que pueda realizar sus actividades.__



**- Administrador Global de Azure AD:** Tiene control completo del directorio activo. Tomar en cuenta que se maneja informaci贸n sensible, habilitar segundo factor de autenticaci贸n es la mejor opci贸n para mantener protegida la informaci贸n.


**- Suscripci贸n de Azure:** Da acceso a ciertos servicios en la nube, normalmente se asocia con un directorio activo.

**- Inquilino de Azure:** Directorio activo donde se cre贸 el usuario. Con sus credenciales, el usuario podr谩 hacer uso de las aplicaciones activas dentro de este directorio, ejemplo: control de n贸mina e inventarios en caso que esta app se encuentre registrada dentro del directorio y le damos acceso al usuario, se convierte en inquilino individual.

**- Multi inquilino:** Permite colaborar en diferentes organizaciones.

**- Directorio de Azure AD:** Instancia de AD directamente en nuestro tenant (inquilino), de esta manera se tiene acceso al dominio del directorio activo, grupos de usuarios, informaci贸n, habilitar autenticaci贸n, se tiene acceso al AD asociado a nuestra cuenta.

**- Dominio Personalizado:** Nombre de la organizaci贸n

**- Cuenta Microsoft (MSA):** Asociada a servicios como Outlook, hotmail, etc.

##### 2. Componentes de la Autenticaci贸n - 馃槂

**- Autenticacion:** Comprobar o autenticar las credenciales cuando un usuario inicia sesi贸n en un dispositivo, app o servicio.

**- Componentes:** Restablecimiento de la contrase帽a de autoservicio (todo automatico sin intervencion humana, como llamadas o sms)

**- Autenticacion multifactor:** Codigos sms, correos, llamadas, codigos.

**- Integracion hibrida y autenticacion sin contrase帽as:** no escribir contrase帽a siempre, se puede registrar dispositivo y usar autenticacion biometrica como huella. voz.

**- Restablecimiento contrase帽a:**

    - Cambio contrase帽a.
    - Restablecimiento contrase帽a.
    - Desbloqueo cuenta.

**- Proteccion con contrase帽a:**

    - Bloqueo contrase帽as no seguras
    - Definir directivas de protecci贸n
    - Seguridad hibrida: se sincroniza on premises y online las directivas para aceptar contrase帽as.

**- Complejidad contrase帽a:**

    - Contrase帽a que cumpla con reglas de complejidad
    - Azure AD usa combinacion predeterminada que se puede personalizar. una letra minuscula, mayuscula, numero, simbolo.
    - Cambiar contrase帽a cuando se olvida o perdiodicamente.
    _ Bloqueo inteligente cuenta. evita intentos de adivinar por fuerza bruta. se desbloquea con el admin o usuario designado.

**- Autenticacion sin contrase帽a:**

    - Conveniente - seguro: password. se puede hackear facilmente.
    - Conveniente + seguridad: password + 2 factor
    - Conveniente + seguro: sin password. se pone usuario e inicia sesion. asi AD se conecta con app authenticator y valida identidad. biometrico, pin, codigo


#### 3. 驴Qu茅 es la autenticaci贸n multifactor? 馃槂

El funcionamiento de la autenticaci贸n multifactor se basa en exigir uno o mas de los siguientes elementos:

- Algo que se conoce
- Algo que tiene
- Algo que forma parte de ti

**Acceso condicional:**

- Ubicaci贸n de inicio de sesi贸n
- Las caracter铆sticas de detecci贸n de riesgos de Azure Ad Identy Protection incluten el reporte de usuarios en riesgo e inicios de sesi贸n riesgosos.
- Adicionalmente se pueden crear directivas de acceso condicional que utilicen esas detecciones para determinar las acciones correspondientes.
- Toma en cuenta Se帽ales
- Toma decisiones con las se帽ales
- Realiza el cumplimiento


![Screen Shot 2022-03-05 at 14 30 31](https://user-images.githubusercontent.com/38354463/156899107-42d21ec2-6b60-4a83-aea0-96e34bbbaf6e.png)

Fuente: Curso de Azure Active Directory www.platzi.com



#### 4. Autenticaci贸n vs Autorizaci贸n 馃槂

**-Autenticaci贸n:**

鈥? Consiste en demostrar que eres quien dices ser. La plataforma de identidad de Microsoft utiliza el protocolo OpenID Connect para administrar la autenticaci贸n.

**- Autorizaci贸n**

鈥? Consiste en conceder a una parte autenticada permiso para hacer algo. Se especifica que datos se pueden acceder y que se puede hacer con ellos. La plataforma de identidad de Microsoft utiliza OAuth 2.0

**- Combinando autenticaci贸n y autorizaci贸n**

Delegando la autenticaci贸n y autorizaci贸n de Azure AD permite los siguientes escenarios:

- Directivas de acceso condicional
- Uso de autenticaci贸n multifactor
- Inicio de sesi贸n 煤nico (SSO)

**- Protocolos de autenticaci贸n:**

- OAuth frente a OpenID Connect
- OAuth frente a SAML
- OpenID Connect frente a SAML


#### 5 Hablemos de Tokens

Un token en inform谩tica es una cadena de caracteres que tienen un significado coherente en cierto lenguaje de programaci贸n.

**- Tokens de ID:** Los tokens de Id de env铆an a la aplicaci贸n cliente como parte de un flujo de OpenID Connect. Este tipo de token sirve para autenticar al usuario a validar que un usuario es quien dice ser.

**- Token de Acceso:** Es un token de seguridad emitido por un servidor de autorizaci贸n como parte de un flujo de OAuth 2.0, incluye informaci贸n sobre el usuario y el recurso para el que est谩 previsto el token.

**- Token de actualizaci贸n:** Los tokens de acceso solo son validos durante un breve periodo de tiempo, utiliza tokens de actualizaci贸n en la aplicaci贸n cuando sea necesario.

**- Validaci贸n de tokens de seguridad:** La validaci贸n del token la realiza la aplicaci贸n para la cual fue generada. Esto ocurre al comprobar la firma generada utilizando la llave p煤blica del servidor de autorizaci贸n.

**- Normalmente el servidor de autorizaci贸n proporciona un par de tokens.** 

**- Token de acceso para acceder a la aplicaci贸n o al recurso protegido.**

**- Token de actualizaci贸n, se utiliza para renovar el token de acceso cuando esta a punto de expirar.**

**- Instancias de JSON WEB Token y Notificaciones:**

- La plataforma de identidad de Microsoft implementa los tokens de seguridad como instancias de JSON Web Tokens (JWT) que incluyen notificaciones.
- Una notificaci贸n proporciona aserciones sobre una entidad, como aplicaci贸n cliente o el propietario de recursos a otra entidad.
- Las notificaciones son pares de nombres o valores que se transmiten datos sobre el firmante del token.
- Las aplicaciones puedes usar las notificaciones para tareas como:

o Validar token
o Identificar el inquilino firmante del token
o Mostrar informaci贸n del usuario
o Determinar la autorizaci贸n del firmante

**Una notificaci贸n se compone de pares clave-valor que proporcionan informaci贸n como:**

- El servidor de tokens de seguridad que genero el token
- La fecha en que se gener贸 el token
- El firmante
- La audiencia, que es la aplicaci贸n para la cual se gener贸 el token
- La aplicaci贸n (Cliente) que solicito el token.

M谩s informaci贸n en Azure Documentation: https://docs.microsoft.com/es-mx/azure/active-directory/develop/security-tokens


#### 6. Introducci贸n a la biblioteca de autenticaci贸n MSAL

La biblioteca de autenticaci贸n de Microsoft (MSAL) permite que los desarrolladores adquieran tokens desde la plataforma de identidad para autenticar usuarios y acceder a API web protegidas.

Te facilitara el acceso a Microsoft Graph y Otras APIs de Microsoft

Ventajas de MSAL

鈥? No tienes que usar directamente las bibliotecas OAuth de manera manual
鈥? Adquiere tokens en nombre de un usuario o en nombre de la aplicaci贸n
鈥? Mantiene en cach茅 tokens y actualiza los tokens en nombre del usuario antes que expiren.
鈥? Ayuda a configurar la aplicaci贸n mediante app settings

Escenarios y tipos de aplicaci贸n:

MSAL se puede usar en varios escenarios, incluyendo:

鈥? Aplicaciones de una sola p谩gina utilizando JavaScript
鈥? Aplicaciones web que inicia sesi贸n de usuarios.
鈥? Aplicaciones web que inician sesi贸n de un usuario y llamada a una API Web
鈥? Protecci贸n de una API Web
鈥? Api web que llama a otra Api Web en nombre del usuario.

Lenguajes y plataformas de MSAL:

鈥? Android
鈥? Angular
鈥? iOS y macOS
鈥? JAVA de MSAL
鈥? .Js
鈥? .Net
鈥? Node
鈥? Python
鈥? React


### 7. Caracter铆sticas de Azure Active Directory B2C

Un inquilino representa la organizaci贸n y es un directorio de usuarios. Los recursos asociados con un inquilino de Azure Ad B2C incluyen:

鈥? Directorio
鈥? Registros de aplicaci贸n
鈥? Flujos de usuario y directivas personalizadas
鈥? Proveedores de identidad
鈥? Claves

**Cuentas en Azure AD B2C:**

En Azure Ad B2C se definen varios tipos de cuentas de usuario, incluyendo:

鈥? Cuentas profesionales
鈥? Cuentas de invitado
鈥? Cuenta de consumidor

Opciones de inicio de sesi贸n en la cuenta local

**Azure AD B2C proporciona varias maneras en la que los usuarios se pueden autenticar, incluyendo:**

鈥? Cuenta local con el nombre de usuario y contrase帽a
鈥? Comprobaci贸n por tel茅fono (autenticaci贸n sin contrase帽a)
鈥? Cuenta local utilizando correo electr贸nico y contrase帽a

**Atributos del perfil del usuario:**

鈥? Azure AD B2C permite administrar los atributos comunes de los perfiles de cuentas de consumidor (nombre, apellidos, ciudad, etc.)
鈥? Se puede ampliar el esquema de Azure Ad para almacenar informaci贸n adicional.

**Experiencias de identidad:**

鈥? Define la l贸gica de negocios que siguen los usuarios para obtener acceso a una aplicaci贸n.
鈥? Determinar la serie de pasos que se siguen para iniciar sesi贸n, registrarse, editar un perfil o restablecer una contrase帽a.
鈥? Las dos formas de experiencia de los usuarios son:
o Flujos de Usuario
o Directivas personalizadas

**Flujos de usuario**

鈥? Son directivas configurables, predefinidas e integradas que se proporcionan para crear experiencias de registro, inicio de sesi贸n, editar perfil o restablecer contrase帽a.
