# animaciones-css

Iniciando el curso de aniamciones con css
cursode transformaciones en css

Enlaces con información de transiciones, animaciones y transformaciones

https://static.platzi.com/media/public/uploads/animaciones_5bda2325-fb2e-4060-9751-5863d226fcf1.pdf

https://static.platzi.com/media/public/uploads/transformaciones_en_2d_y_3d_d712736c-5368-4c9b-8827-331dc347d536.pdf

https://static.platzi.com/media/public/uploads/transiciones_2093f06d-4937-4ba1-999d-73e1b9a56cca.pdf


pseudo clases con : 
Pseudo elementos con :: 

pagina de colores
https://htmlcolorcodes.com/


curvas de acelaración
https://easings.net/

https://cubic-bezier.com/#.17,.67,.83,.67

https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function

https://developer.mozilla.org/es/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context



Pagina de gradientes
https://cssgradient.io/gradient-backgrounds/

backface visibility
https://developer.mozilla.org/en-US/docs/Web/CSS/backface-visibility
https://www.w3schools.com/cssref/trycss3_backface_inuse.htm

transiciones
https://static.platzi.com/media/public/uploads/transiciones_2a4663d3-d90c-4b27-a69d-228c9a767b40.pdf

https://developer.mozilla.org/en-US/docs/Web/CSS/transition



Propiedades recomendadas y no recomendadas para animar

Al hacer animaciones debemos fijarnos que no sean demasiado costosas computacionalmente para que no parezcan inestables y poco fluidas.

Para ello, debemos comprender un concepto clave llamado: el proceso de renderizado.

Resulta que, como el navegador no entiende el código que hacemos, debe hacer una transformación de ese código para que finalmente pueda ser entendido y visualizado en la pantalla.

Esa transformación se hace en una serie de pasos como los que puedes ver a continuación:

Javascript-style-Layout-paint-composite

https://csstriggers.com/

Sin embargo, los pasos que nos interesan en este momento son los últimos 3: Layout, Paint y Composite. Cada uno cumple un papel muy importante, pero no todas las propiedades pasan por estos 3 procesos.

Si una propiedad debe pasar por el paso de Layout, obligatoriamente debe pasar por Paint y Composite también. Si una propiedad debe pasar por el paso de Paint, obligatoriamente debe pasar por Composite también. Pero, si una propiedad debe pasar por el paso de Composite, no debe pasar por ningún otro paso.

Con lo anterior, podemos darnos cuenta de que hay propiedades que requieren un costo mayor que otras al tener que pasar por más pasos. Puedes revisar el proceso de renderizado que realiza cada propiedad en esta página: https://csstriggers.com/. Revisemos algunas de ellas:

Propiedad height: En cada uno de los motores de renderizado, podemos darnos cuenta por la imagen de abajo que requiere de los pasos de Layout, Paint y Composite, lo cual es bastante costoso.

Propiedad background-color: Es una propiedad que no afecta el diseño (Layout) pero requiere una nueva capa de pintura (Paint), lo cual la hace una propiedad también costosa.

Propiedades transform y opacity: Estas dos propiedades sólo requieren del paso de Composite, lo cual las hace muy baratas de animar. Si necesitas modificar propiedades como width y left (propiedades costosas), puedes reemplazarlas usando la propiedad transform para tratar de lograr el mismo efecto.

Finalmente, si sabemos por cuáles pasos de renderizado pasa cada una de las propiedades, sabremos con exactitud cuáles propiedades son más costosas y menos recomendadas para animar (como height, width y background-color), como también, cuáles propiedades son menos costosas y más recomendadas para animar (como transform y opacity).

Te comparto esta lectura por si quieres conocer más a profundidad cómo trabaja el motor de cada navegador con cada uno de los pasos que describimos anteriormente: https://hacks.mozilla.org/2017/08/inside-a-super-fast-css-engine-quantum-css-aka-stylo/

