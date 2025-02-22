Bueno Ricki, el lunes te muestro todo como quedo y avanzamos con la siguiente tarea.
Primero te voy a mostrar lo que hice, como esta todo funcionando y despues voy a dar una reflexion de como estoy sintiendo esta primera semana.


La tarea es = Crear un nuevo plan de stripe (subscripcion) para el Early Access en la Landing-page.
Si el usuario NO tiene cuenta, hacer una peticion a portal para registar el usuario, posteriormente iniciar sesion, para poder guardar los tokens y guaradar el uid en una DBTemporal asi se puede crear el custoemr correctamente. 

Si el usuario esta con sesion iniciada, y tiene por ejemplo un plan "starter" hacer el checkout correctamente y cambiarle el plan starter a Early-acces. (Debido que starter era el antiguo y early-acces es el ultimo comprado).

Actualizar en el front en la parte de /netsocks/proxy/zones , el estado de starter a early_access.
Tambien faltaria.


Si el usuario es nuevo y se crea la cuenta, una vez que se haga el checkout redireccionar correctamente a netsocks/proxys.

Diferenciar entre subscription y payment de stripe, porque si no tenia un error a la hora de recargar creditos debido que siempre se trataba el estado como subscription y ya se arreglo.

Ahora voy a mandarte unas fotos de todo el flujo asi ves como quedo.

-----


FLUJO CON USUARIO NO INICIADO SESION

A la hora de apretar el boton get-early-acces en la consola muestra eso para identificar si esta logeado o no.

![[Pasted image 20250222151335.png]]


Una vez se paga en stripe. 
Nos redirige a la url http://localhost:5175/netsocks/proxy

![[Pasted image 20250222151517.png]]

Y en la parte de zones aparece asi. 


![[Pasted image 20250222151559.png]]

Y si recargo creditos se queda el plan early_acces y se agregan los creditos.

![[Pasted image 20250222151649.png]]



-----

FLUJO CON USUARIO INICIADO SESION

![[Pasted image 20250222151846.png]]

Cuando hacemos el flujo de checkout si estamos iniciado sesion, se autocompleta el email.
(Tambien pasa en la parte de recargar creditos de proxy , me olvide de mostrarlo lo voy a mostrar ahora)
![[Pasted image 20250222151938.png]]

(ESTADO DEL PLAN ANTES DE HACER EL CHECKOUT)
![[Pasted image 20250222152316.png]]

(ESTADO DEL PLAN DEPSUES DE HACER EL CHECKOUT)

![[Pasted image 20250222152412.png]]

(Y SI SE CARGA CREDITOS SE MANTIENE EL PLAN EARLY_ACCES)