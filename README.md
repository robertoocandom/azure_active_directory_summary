# Azure Active Directory Summary
 Resumen: Azure Active Directory Puntos Importantes para su implementación


##### 1. Terminología Clave de AD - 😃

**- Identidad:** algo que se puede autenticar. Ej: Para un usuario final puede ser user ID o correo electrónico y contraseña. Para una app puede ser app ID o certificado que se utilice para aplicar la autenticación

**- Cuenta:** Tiene datos asociados a la identidad, una vez que te autenticas puedes tener acceso a nombre de usuario, perfil, a que rol pertenece, diferente información asociada a esa identidad.



> __No existe cuenta sin identidad. Para tener una cuenta se debe tener una identidad.__



**- Cuenta de Azure AD:** Se crea al ocupar un servicio en la nube como portal de Azure, o servicios de Microsoft 365. De esta manera tu identidad (correo electrónico o tu user ID) está registrada en un directorio de Azure AD, así mismo se puede utilizar esta cuenta para hacer uso de correo electrónico, y servicios internos y externos.

**- Administrador de cuenta:** Asociado al administrador que puede realizar o hacer gestión de facturación.

**- Administrador de servicios:** tiene acceso a todos los servicios de suscripción de Azure, puede tener control completo a todos los servicios que están desplegados en la suscripción.

**- Propietario:** Tiene control más detallado sobre algún recurso como app web. Es importante dar los accesos pertinentes con quien se comparten los accesos.



> __Evitar que el usuario pueda eliminar los recursos que creamos.__


> __Dar al usuario el acceso mínimo requerido para que pueda realizar sus actividades.__



**- Administrador Global de Azure AD:** Tiene control completo del directorio activo. Tomar en cuenta que se maneja información sensible, habilitar segundo factor de autenticación es la mejor opción para mantener protegida la información.


**- Suscripción de Azure:** Da acceso a ciertos servicios en la nube, normalmente se asocia con un directorio activo.

**- Inquilino de Azure:** Directorio activo donde se creó el usuario. Con sus credenciales, el usuario podrá hacer uso de las aplicaciones activas dentro de este directorio, ejemplo: control de nómina e inventarios en caso que esta app se encuentre registrada dentro del directorio y le damos acceso al usuario, se convierte en inquilino individual.

**- Multi inquilino:** Permite colaborar en diferentes organizaciones.

**- Directorio de Azure AD:** Instancia de AD directamente en nuestro tenant (inquilino), de esta manera se tiene acceso al dominio del directorio activo, grupos de usuarios, información, habilitar autenticación, se tiene acceso al AD asociado a nuestra cuenta.

**- Dominio Personalizado:** Nombre de la organización

**- Cuenta Microsoft (MSA):** Asociada a servicios como Outlook, hotmail, etc.

##### 2. Componentes de la Autenticación - 😃

**- Autenticacion:** Comprobar o autenticar las credenciales cuando un usuario inicia sesión en un dispositivo, app o servicio.

**- Componentes:** Restablecimiento de la contraseña de autoservicio (todo automatico sin intervencion humana, como llamadas o sms)

**- Autenticacion multifactor:** Codigos sms, correos, llamadas, codigos.

**- Integracion hibrida y autenticacion sin contraseñas:** no escribir contraseña siempre, se puede registrar dispositivo y usar autenticacion biometrica como huella. voz.

**- Restablecimiento contraseña:**

    - Cambio contraseña.
    - Restablecimiento contraseña.
    - Desbloqueo cuenta.

**- Proteccion con contraseña:**

    - Bloqueo contraseñas no seguras
    - Definir directivas de protección
    - Seguridad hibrida: se sincroniza on premises y online las directivas para aceptar contraseñas.

**- Complejidad contraseña:**

    - Contraseña que cumpla con reglas de complejidad
    - Azure AD usa combinacion predeterminada que se puede personalizar. una letra minuscula, mayuscula, numero, simbolo.
    - Cambiar contraseña cuando se olvida o perdiodicamente.
    _ Bloqueo inteligente cuenta. evita intentos de adivinar por fuerza bruta. se desbloquea con el admin o usuario designado.

**- Autenticacion sin contraseña:**

    - Conveniente - seguro: password. se puede hackear facilmente.
    - Conveniente + seguridad: password + 2 factor
    - Conveniente + seguro: sin password. se pone usuario e inicia sesion. asi AD se conecta con app authenticator y valida identidad. biometrico, pin, codigo


#### 3. ¿Qué es la autenticación multifactor?

El funcionamiento de la autenticación multifactor se basa en exigir uno o mas de los siguientes elementos:

- Algo que se conoce
- Algo que tiene
- Algo que forma parte de ti

**Acceso condicional:**

- Ubicación de inicio de sesión
- Las características de detección de riesgos de Azure Ad Identy Protection incluten el reporte de usuarios en riesgo e inicios de sesión riesgosos.
- Adicionalmente se pueden crear directivas de acceso condicional que utilicen esas detecciones para determinar las acciones correspondientes.
- Toma en cuenta Señales
- Toma decisiones con las señales
- Realiza el cumplimiento


![Screen Shot 2022-03-05 at 14 30 31](https://user-images.githubusercontent.com/38354463/156899107-42d21ec2-6b60-4a83-aea0-96e34bbbaf6e.png)

Fuente: Curso de Azure Active Directory www.platzi.com



#### 4. Autenticación vs Autorización

**-Autenticación:**

• Consiste en demostrar que eres quien dices ser. La plataforma de identidad de Microsoft utiliza el protocolo OpenID Connect para administrar la autenticación.

**- Autorización**

• Consiste en conceder a una parte autenticada permiso para hacer algo. Se especifica que datos se pueden acceder y que se puede hacer con ellos. La plataforma de identidad de Microsoft utiliza OAuth 2.0

**- Combinando autenticación y autorización**

Delegando la autenticación y autorización de Azure AD permite los siguientes escenarios:

- Directivas de acceso condicional
- Uso de autenticación multifactor
- Inicio de sesión único (SSO)

**- Protocolos de autenticación:**

- OAuth frente a OpenID Connect
- OAuth frente a SAML
- OpenID Connect frente a SAML

