Laboratorio 3 – Construya un Automated Flow para notificar al gerente
cuando se crea un nuevo elemento en Dynamics 365 Business Central

**Objetivo:** En este laboratorio, los participantes aprenderán a crear
un automated flow en Power Automate que manda un email notification
cuando se crea un nuevo elemento en Microsoft Dynamics 365 Business
Central. Al seguir un proceso estructurado, los participantes se
familiarizarán con los triggering flows en función de los datos de
Business Central, recopilando información del elemento pertinente,
insertando conditional logic, y ejecutando acciones para mandar alertas
email. Esta experiencia práctiva le habilitará a aprovechar Power
Automate para mejorar los procesos y notificaciones empresariales.

**Duración estimada:** 15 minutos

Tarea 1: Regístrese en Microsoft Dynamic 365 Business Central

1.  Navegue a
    +++\*\*[*https://www.microsoft.com/en-us/dynamics-365/products/business-central\*\*+++*](https://www.microsoft.com/en-us/dynamics-365/products/business-central**+++) y
    haga clic en **Try for Free.**

> ![](./media/image1.png)

2.  Introduzca su Office 365 tenant ID y haga clic en **Next**.

> ![](./media/image2.png)

3.  Luego, haga clic en **Sign in** e introduzca las credenciales.

> ![](./media/image3.png)

4.  Seleccione **United states** como country or region, introduzca
    su **phone number** y seleccione **Get started**.

> ![](./media/image4.png)

5.  Haga clic en **Get started** para acceder al Business Central.

> ![](./media/image5.png)

6.  Seleccione el botón **Skip Survey** para continuar.

> ![](./media/image6.png)

7.  Se le dirigirá a la página de inicio de Dynamics 365 Business
    Central.

> ![](./media/image7.png)

Tarea 2: Inicie Power Automate

1.  Abra una nueva pestaña junto a Dynamic 365 business central y
    navegue a
    +++\*\*[*https://make.powerautomate.com/\*\*+++*](https://make.powerautomate.com/**+++) en
    su navegador.

> ![](./media/image8.png)

2.  Si le pide, introduzca el **Microsoft 365 tenant id** en el campo
    relevante y haga clic en el botón **Next**.

> ![](./media/image9.png)

3.  Introduzca el **password** en el campo relevante y haga clic
    en **Sign in.**

> ![](./media/image10.png)

4.  Desde la barra de navegación superior, seleccione el
    environment **Dev One.**

> ![](./media/image11.png)

5.  Haga clic en **+Create** en el menú izquierdo.

> ![](./media/image12.png)

6.  Seleccione el **Automated cloud flow** tile.

> ![](./media/image13.png)

Tarea 3: Cree el Trigger en función de los datos de Business Central

1.  En el cuadro **Flow name**, introduzca +++**Email notification for
    new furniture**+++.

> ![](./media/image14.png)

2.  En **Choose your flow's trigger search bar**, introduzca **business
    central**. Baje para ver los triggers y seleccione el trigger **When
    a record is created (V3)**.

3.  Haga clic en **Create**.

> ![](./media/image15.png)

4.  Introduzca los detalles del trigger:

    1.  **Environment name**: introduzca +++**PRODUCTION**+++.

    2.  **Company name**: Seleccione **CRONUS USA, Inc.** desde la
        lista.

    3.  **Table name**: Seleccione **items**.

> ![](./media/image16.png)

Tarea 4: Recopile datos desde Business Central

1.  Haga clic en el botón **+** add y seleccione **Add an action**.

> ![](./media/image17.png)

2.  En la pantalla **Add an action**, tecle +++**Dynamics 365 Business
    Central**+++ en el search box y elija la acción **Get record (V3)**.

> ![](./media/image18.png)

3.  Introduzca la siguiente información:

    1.  **Environment**: +++**PRODUCTION**+++.

    2.  **Company name**: Seleccione **CRONUS USA, Inc.**.

    3.  **Table name**: Seleccione **items**.

    4.  **Row id**: Seleccione el **Row Id** token desde Dynamic
        content.

> ![](./media/image19.png)

Tarea 5: Cree el Condition

1.  Haga clic en el botón **+** debajo de Get record y seleccione **Add
    an action**.

> ![](./media/image20.png)

2.  En el **Add an action** search bar, introduzca **Control**. Elija
    el **Condition** action.

> ![](./media/image21.png)

3.  Establezca el condition:

    1.  En el primer **Choose a value**, seleccione el **Item Category
        Code** token desde Dynamic content.

    2.  Mantenga la opción **is equal to**.

    3.  En el segundo **Choose a value**, introduzca
        +++**FURNITURE**+++.

> ![](./media/image22.png)

Tarea 6: Cree un Action en función del Condition

1.  En la ventana de condition **If yes or True**, haga clic en **Add an
    action**.

> ![](./media/image23.png)

2.  Busque +++**office 365 outlook**+++ en la ventana Add an action y
    haga clic en see more. En el office 365 outlook trigger
    seleccione **Send an Email (V2).**

> ![](./media/image24.png)
>
> ![](./media/image25.png)

3.  Introduzca los detalles del email:

    1.  **To**: Introduzca ‘Admin’ y seleccione **Mod Admin** desde la
        sugerencia, o sea, Office 365 tenant email Id, lo que está
        usando en este laboratorio.

    2.  **Subject**: Introduzca +++**New furniture released**+++.

    3.  **Body**:

        1.  Agregue el texto **New** **furniture**.

        2.  Agregue el token **Number** desde Dynamic content.

        3.  Agregue el token **displayName** desde Dynamic content.

        4.  Agregue el texto +++**has just released.**+++

> ![](./media/image26.png)

4.  Haga clic en **Save** para finalizar su flow.

> ![](./media/image27.png)

Tarea 7: Pruebe el Flow

1.  Desde la barra superior, haga clic en el botón **Test**.

> ![](./media/image28.png)

2.  Seleccione el **Manual** Process y haga clic en **Test**.

> ![](./media/image29.png)

3.  Vuelva al **Business Central website** y desde la barra superior,
    vaya a **Sales** 🡪 **Items**.

> ![](./media/image30.png)

4.  Haga clic en el botón **+ New**

> ![](./media/image31.png)

5.  Seleccione **ITEM**, y haga clic en **OK**.

> ![](./media/image32.png)

6.  En el campo Item Category Code, seleccione **FURNITURE** y en el
    campo Description, escriba **Office Chair.**

> ![](./media/image33.png)

7.  Haga clic en el botón **Save**.

> ![](./media/image34.png)

8.  En el Power Automate portal, haga clic en **App launcher** en la
    esquina superior izquierda. Seleccione **Outlook** y puede ver que
    se ha recibido la respuesta automatizada en el **email** de MOD
    Admin.

> ![](./media/image35.png)

Conclusión:

A finales de este laboratorio, los participantes habrán creado un
automated email notification flow en Power Automate para nuevos
elementos en Business Central. Habrán obtenido una experiencia práctica
en configurar triggers, actions, y conditions, los que son habilidades
necesarias para automatizar los workflows. Los participantes también
comprenderán cómo recopilar y manipular datos de Business Central de
manera effectiva, habilitándole a agilizar y mejorar la productividad en
sus organizaciones. Este conocimiento funciona como una base para
explorar más las capacidades de Power Automate para automatizar varios
procesos empresariales.
