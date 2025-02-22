Bueno Ricki, el lunes te muestro todo como quedó y avanzamos con la siguiente tarea. Primero te voy a mostrar lo que hice, cómo está todo funcionando y después voy a dar una reflexión de cómo estoy sintiendo esta primera semana.

La tarea es = Crear un nuevo plan de Stripe (suscripción) para el Early Access en la Landing-page. Si el usuario NO tiene cuenta, hacer una petición a portal para registrar el usuario, posteriormente iniciar sesión, para poder guardar los tokens y guardar el uid en una DB temporal así se puede crear el customer correctamente.

Si el usuario está con sesión iniciada, y tiene por ejemplo un plan "starter", hacer el checkout correctamente y cambiarle el plan starter a Early-access. (Debido a que starter era el antiguo y early-access es el último comprado).

Actualizar en el front en la parte de /netsocks/proxy/zones, el estado de starter a early_access. También faltaría.

Si el usuario es nuevo y se crea la cuenta, una vez que se haga el checkout redireccionar correctamente a netsocks/proxys.

Diferenciar entre subscription y payment de Stripe, porque si no tenía un error a la hora de recargar créditos debido a que siempre se trataba el estado como subscription y ya se arregló.

Ahora voy a mandarte unas fotos de todo el flujo así ves cómo quedó.

### FLUJO CON USUARIO NO INICIADO SESIÓN

A la hora de apretar el botón get-early-access en la consola muestra eso para identificar si está logeado o no.

![Pasted image](https://github.com/Santinou1/docs-rick/blob/main/Pasted%20image%2020250222151335.png)

Una vez se paga en Stripe, nos redirige a la URL [http://localhost:5175/netsocks/proxy](http://localhost:5175/netsocks/proxy)

![Pasted image](https://github.com/Santinou1/docs-rick/blob/main/Pasted%20image%2020250222151517.png)

Y en la parte de zones aparece así.

![Pasted image](https://github.com/Santinou1/docs-rick/blob/main/Pasted%20image%2020250222151559.png)

Y si recargo créditos, se queda el plan early_access y se agregan los créditos.

![Pasted image](https://github.com/Santinou1/docs-rick/blob/main/Pasted%20image%2020250222151649.png)

### FLUJO CON USUARIO INICIADO SESIÓN

![Pasted image](https://github.com/Santinou1/docs-rick/blob/main/Pasted%20image%2020250222151846.png)

Cuando hacemos el flujo de checkout si estamos iniciados en sesión, se autocompleta el email. (También pasa en la parte de recargar créditos de proxy, me olvidé de mostrarlo)

![Pasted image](https://github.com/Santinou1/docs-rick/blob/main/Pasted%20image%2020250222153611.png)

**Estado del plan antes de hacer el checkout:**

![Pasted image](https://github.com/Santinou1/docs-rick/blob/main/Pasted%20image%2020250222152316.png)

**Estado del plan después de hacer el checkout:**

![Pasted image](https://github.com/Santinou1/docs-rick/blob/main/Pasted%20image%2020250222152412.png)

**Y si se cargan créditos, se mantiene el plan early_access.**
