# Buenas prácticas para bots de Discord.
*Este repositorio es básicamente un fork de [discord-bot-best-practices](https://github.com/meew0/discord-bot-best-practices/) pero traducido al Español y actualizado para seguir la [nueva política de privacidad para desarrolladores](https://discord.com/developers/docs/policy).
*Importante: Estas pautas están destinadas a bots en servidores públicos. Si su bot es privado seguramente no le sea aplicable.*

1. **Los comanandos deben ser llamados explícitamente.** 
    Los bots no deberían responder o ser llamados en un chat normal. Debe usar un prefijo para los comandos o solo responder cuando su bot es @mencionado.

2. **Utilice prefijos únicos.** 
  Los prefijos de un solo carácter como `!`, `$` y `.` son comunes para ejecutar comandos y dan lugar a coincidencias y problemas con otros bots. Si opta por usar un prefijo para su bot, considere usar palabras (`estrella`) o caracteres Unicode únicos (`¨`). Además, debes evitar usar `#` o `@` como prefijos, ya que pueden usarse para mencionar un canal o un miembro. Idealmente, el prefijo de su bot debe ser configurable servidor por servidor, de modo que los propietarios del servidor puedan asegurarse de que cada bot tenga su propio prefijo único de su elección.

3. **No seas codicioso.** 
  Limítese a una pequeña cantidad de prefijos para reducir el riesgo de coincidencias con otros.

4. **No abuses de las menciones.** 
  Si responde directamente a un comando, no use una mención, pueden crear bucles de respuestas. Las menciones están bien si se ejecuta un comando de larga duración, los mensajes privados son una buena alternativa.

5. **Tenga un comando de `info/botinfo`.** 
  Debe proporcionar información sobre el bot, como qué librería está usando y la versión utilizada, comandos de ayuda (`help`) y, lo más importante, quién lo creó.

6. **No responda con "comando no válido".** 
  Si un usuario usa un comando que no existe, déjelo fallar silenciosamente. No haga que responda con algo como "comando no válido". Aunque si el comando es correcto, pero los argumentos son incorrectos, entonces está bien responder con "argumentos no válidos". Si hay más de un bot en un servidor que comparte un prefijo, esto puede resultar en un uso muy desagradable. Si el prefijo de su bot es configurable, esta regla probablemente se pueda ignorar de manera segura.

7. **Sea respetuoso con la API de Discord.**
  Los bots que abusan y hacen mal uso de la API de Discord arruinan las cosas para todos. Respete los [Términos de servicio](https://discord.com/terms), las [Directivas de la comunidad](https://discord.com/guidelines) y [Política de privacidad para desarrolladores](https://discord.com/developers/docs/policy). Asegúrese de tener en cuenta la limitación de velocidad y la retirada en el código de su bot, y sea inteligente al usar la API. Asegúrese de pedir ayuda si no está seguro de la forma correcta de implementar las cosas. Recuerde añadir "tiempos de espera" o "intervalos" para evitar abusar de la API de Discord.

8. **Ignore sus propios mensajes y los de otros bots.**
  Esto ayuda a prevenir bucles infinitos y posibles vulnerabilidades de seguridad. Usar un espacio "invisible" como `\u200B` y `\u180E` al comienzo de cada mensaje también evita que su bot active los comandos de otros bots. La API de Discord también le dice si un usuario es un bot (propiedad `bot` en el objeto `User`, [referencia](https://discord.com/developers/docs/resources/user#user-object)).

9. **Mantenga las funciones [NSFW](https://support.discord.com/hc/es/articles/115000084051) solo en canales [NSFW](https://support.discord.com/hc/es/articles/115000084051)**
  Todos los comandos/funciones NSFW solo deberían funcionar en canales marcados como NSFW.

10. **Use las menciones al bot para ayudar a los usuarios.**
  Permitir una mención como prefijo ("@Bot ayuda") o agregar una forma de encontrar el prefijo del bot con solo una mención ("@Bot" o "@Bot prefijo" ) ayudará a los usuarios que son nuevos en su bot a comenzar. (Asegúrate de que sea cual sea el mensaje, se encuentra fácilmente. Una excelente manera de hacerlo es incluyéndolo en presencia de tu bot). Además, una mención es el prefijo más exclusivo de todos.

11. **Sea cuidadoso con los datos.**
  Asegúrese de ser cuidadoso con los datos que recibe de la API de Discord. De ninguna manera intente dirigirse a los usuarios para mostrar publicidad, vender datos de los usuarios, revelar datos sensibles de los usuarios sin su consentimiento, alentar o promover actividades ilegales. Y un largo etcétera que [puede consultar](https://discord.com/developers/docs/policy).

Si tiene alguna idea para agregar a estas pautas, abra un issue o una pull request para hablarlo.
