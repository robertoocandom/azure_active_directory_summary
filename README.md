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


