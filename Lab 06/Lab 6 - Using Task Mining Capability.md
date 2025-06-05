Laboratorio 6 - Usar Task Mining Capability para analizar el Order
Fulfillment Process

**Objetivo:** El laboratorio se centra en utilizar los Power Automate
task mining capabilities para analizar y optimizar el order fulfilment
process. Los participantes aprenderán a importar una solución que
contiene grabaciones de muestra, explorar task mining features, y
realizar process analysis para identificar bottlenecks. Además, el
laboratorio cubre los pasos del proceso de automatización y utilizando
analíticas para obtener insights de la eficacia del proceso.

**Duración estimada:** 30 minutos

**Tarea 1: Prepárese para task mining**

1.  **Inicie sesión en** Power Automate en
    +++\*\*[*https://make.powerautomate.com/\*\*+++*](https://make.powerautomate.com/**+++) con
    sus Office 365 tenant credentials.

2.  Seleccione su environment – **Dev One**.

> ![](./media/image1.png)

Tarea 2: Importe una solución

1.  En el panel de navegación a la izquierda, seleccione **Solutions** y
    luego en el toolbar en la parte superior, seleccione **Import
    solution**.

> ![](./media/image2.png)

2.  Seleccione **Browse**.

> ![](./media/image3.png)

3.  Seleccione el **Processmining.zip** file desde C:\Lab Files y
    ábrelo.

> ![](./media/image4.png)

4.  Seleccione **Next**.

> ![](./media/image5.png)

5.  Seleccione **Import** y espere a que se importe la solución.

> ![](./media/image6.png)

Tarea 3: Visualice los sample recordings

1.  Una vez que importe el .zip file, en el panel de navegación
    izquierdo, seleccione **Process mining** y luego
    seleccione **Invoice submission process**.

> ![](./media/image7.png)

2.  Si navega a la pestaña Analytics, vaya un paso atrás. Vaya
    a **Invoice submission process** al seleccionarlo en la parte
    superior de la página.

> ![](./media/image8.png)

3.  Puede ver algunos de los recordings existentes en **Recordings**.

> ![](./media/image9.png)

4.  Para asegurarse de ver la lista completa de grabaciones existentes,
    seleccione **See all**.

Tarea 4: Explore las características

Verá los siguientes features:

- **New recording**: Crear una nueva grabación.

- **Analytics**: Ver el process map y la información

- **Analyze**: Analizar un proceso.

- **Create activity names**: Crear nombres de actividad para su proceso.

- **Delete process**: Eliminar el proceso.

> ![](./media/image10.png)

Tarea 5: Analizar un proceso

Cuando analiza un proceso, el process mining capability analiza los
recordings existentes para identificar cualquier bottleneck dentro del
proceso de negocios.

1.  Seleccione **Analyze**.

> **Ojo:** El análisis llevará unos minutos en completar. Durante el
> proceso, se ve un status message debajo del botón **New recording**.
>
> ![](./media/image11.png)

2.  Si se encuentra con un error durante la etapa de análisis,
    seleccione **Analyze** para activar esta acción de nuevo.

3.  Una vez hecho, verá el **Process analysis status** cambiando
    a **Analyzed**. Seleccione **Analytics** para ver el process map e
    insights.

> ![](./media/image12.png)
>
> **Ojo:** Este paso puede tardar un par de minutos en completarse
> después de que se haya realizado el análisis.

Tarea 6: Analytics page layout

Esta sección explora lo que puede hacer en la pantalla **Analytics**.

![](./media/image13.png)

![](./media/image14.png)

**Legend:**

1.  **Automate activities**: Para agilizar el proceso de automatización,
    puede usar el **Automate activities** feature. Esta característica
    detecta si el usuario realiza acciones usando una aplicación que
    tiene Power Automate actions disponibles, como Microsoft Outlook o
    Excel. Al seleccionar **Automate activities**, se genera un borrador
    de Power Automate process que contiene acciones relevantes. El
    usuario puede modificar y personalizar el draft process para crear
    el automated process final.

2.  **Legend**: Información adicional sobre el informe, que les ayuda a
    comprender mejor las visualizaciones y los datos presentados.

3.  **Process**: Información detallada sobre el proceso analizado,
    incluido el process map, análisis de tiempo para cada variante y
    cada autor de grabación.

4.  **Application**: Información sobre las aplicaciones utilizadas en
    las grabaciones. Esto incluye qué aplicaciones usaron los autores,
    con qué frecuencia se usaron y cuáles fueron las transiciones entre
    ellas. En este informe se explica qué conectores se deben usar al
    implementar la automatización para el proceso y dónde usar
    potencialmente los flujos de escritorio, ya que no existe ningún
    conector.

Tarea 7: Business process step relationships

Verá los distintos pasos del proceso de negocio y sus duraciones
relacionadas. Estos pasos incluyen:

- Download invoice attachment from email (48 seconds)

- Open Excel invoice list (11.5 seconds)

- Open invoice from OneDrive (21 seconds)

- Enter invoice details (53.6 seconds)

- Save and submit (9 seconds)

- Notify team of submission (26.67 seconds)

> ![](./media/image15.png)

Tarea 8: Visualizar datos de analytics

1.  Echa un vistazo a los principales datos analíticos. El tiempo medio
    de proceso es de 1,47 minutos de cinco recordings.

> ![](./media/image16.png)

2.  Analice otros paneles de métricas basadas en el tiempo.

> **Activity by average time in sec**: Note que **Enter invoice
> details** y **Download invoice** son los que más tiempo están
> tardando.
>
> ![](./media/image17.png)
>
> **Recording by average time in min**: Note que algunos (**Preston
> Morales** y **Shakti Menon**) tardan más que otros.
>
> ![](./media/image18.png)

3.  Seleccione la pestaña **Application** para ver los detalles de
    cuáles aplicaciones se usaron.

> Puede tardar un poco en cargar los informes.

- Al proporcionar información sobre las aplicaciones utilizadas en un
  proceso de negocio, su frecuencia de uso y la cantidad de tiempo
  dedicado a cada aplicación, este informe es crucial para obtener
  información sobre el proceso.

- Por ejemplo, el panel muestra que una aplicación de facturación
  heredada, Outlook y Excel tienen contribuciones significativas al
  tiempo empleado y las acciones de las aplicaciones.

- Tómese su tiempo para familiarizarse con los diferentes informes.

> ![](./media/image19.png)

4.  Vuelva al process map al seleccionar **Process**.

5.  Eche un vistazo a la función de actividades automatizadas. En el
    process map, se puede ver que la capacidad de minería de procesos ha
    destacado varias actividades como posibles candidatas para la
    automatización basada en aplicaciones.

6.  Empiece a crear un flow para la automatización al
    seleccionar **Automate activities** en la parte superior.

> ![](./media/image20.png)
>
> Se abre una pestaña en el navegador y muestra el flow designer. Las
> acciones recomendadas que coinciden con las actividades del process
> map aparecen automáticamente en el panel derecho. Por ejemplo, se
> sugieren varios conectores de email para que los utilice con el fin de
> automatizar el **Download invoice attachment from email** activity.
>
> ![](./media/image21.png)

Conclusión:

En este laboratorio, los participantes utilizaron Power Automate task
mining capabilities para analizar y optimizar el order fulfillment
process. Al importar un pre-built solution con sample recordings,
Exploraron las características clave de task mining, incluyendo process
analysis, identificando bottlenecks, y generando las recomendaciones de
automatización. Los participantes aprendieron a evaluar la eficiencia de
los procesos a través de análisis detallados sobre el tiempo dedicado a
diversas tareas y aplicaciones. El laboratorio destacó cómo task mining
puede agilizar business processes al identificar las oportunidades de
automatización, en última instancia, mejorando la eficiencia operativa y
reduciendo las cargas de trabajo manuales en el proceso de cumplimiento
de pedidos.
