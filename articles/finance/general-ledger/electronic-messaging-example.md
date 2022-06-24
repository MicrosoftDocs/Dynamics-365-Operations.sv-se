---
title: Konfigurera och köra bearbetning för att anropa ett enkelt ER-exportformat med syfte att generera en Excel-rapport
description: I det här ämnet ges ett exempel som visar hur du konfigurerar och använder elektroniska meddelanden.
author: liza-golub
ms.date: 07/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 9894aabde854189e6fc1b6bb62051747f190e3ec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904598"
---
# <a name="set-up-and-run-processing-to-call-a-simple-exporting-er-format-to-generate-an-excel-report"></a>Konfigurera och köra bearbetning för att anropa ett enkelt ER-exportformat med syfte att generera en Excel-rapport

[!include [banner](../includes/banner.md)]

När du har skapat ett ER-format, mappat det till datakällor och slutfört det kan du köra det från arbetsytan **Elektronisk rapportering**. När rapporten har genererats kan du spara den lokalt.

Om du vill kontrollera följande aspekter av rapporteringsprocessen måste du konfigurera bearbetning av elektroniska meddelanden:

- Logga information om som genererade rapporten.
- Logga information om när rapporten genererades.
- Spara rapporter som har skapats för tidigare perioder.

Följande exempel visar hur du kan konfigurera elektroniska meddelanden för att generera en rapport baserad på ett exporterande ER-format för Microsoft Excel. Om du vill följa det här exemplet måste det exporterande ER-formatet för Excel redan ha skapats, mappats till datakällor och slutförts. Dessutom måste en nummerserie redan ha ställts in för elektroniska meddelanden.

När du skapar bearbetning, är det viktigt att du först definierar åtgärder för bearbetning och status som ska ställas in. Följande bild visar bearbetningen för detta exempel.

![Schemat för bearbetning](media/processing-scheme.png)

## <a name="create-message-statuses"></a>Skapa meddelandestatus

1. Gå till **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Meddelandestatus**.
2. Skapa följande meddelandestatusar:

    - Ny
    - Förberedd
    - Skapad

    ![Meddelandestatus](media/message-statuses.png)

3. På raden för statusen **Ny** markerar du kryssrutan **Tillåt borttagning** för att låta användarna ta bort meddelanden som har denna status.

## <a name="create-additional-fields"></a>Skapa ytterligare fält

1. Gå till **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Ytterligare fält**.
2. Lägg till ytterligare fält och dess värden.
3. Ange alternativet **Användarredigering** till **Ja** för att låta användarna redigera fältet.

![Ytterligare fält](media/additional-fields.png)

## <a name="create-message-processing-actions"></a>Skapa åtgärder för meddelandebearbetning

I det här exemplet skapar du följande åtgärder för meddelandebearbetning:

- **Skapa ett meddelande**
- **Uppdatera till förberedd**
- **Generera rapport**
- **Uppdatera till ursprunglig status** (valfritt)

Följ dessa steg om du vill skapa åtgärderna..

1. Gå till **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **Åtgärder för meddelandebearbetning**.
2. Skapa en åtgärd med namnet **Skapa meddelande**. På snabbfliken **allmänna** i fältet **åtgärdstyp** väljer du **skapa ett meddelande**.
3. Skapa en åtgärd med namnet **uppdatera till förberedd** och ange följande fält:

    - På snabbfliken **allmänna** i fältet **åtgärdstyp** väljer du **Användares bearbetning på meddelandenivå**.
    - På snabbfliken **Ursprunglig status** i fältet **meddelandestatus** väljer du **ny**.
    - På snabbfliken **Resultatstatus** i fältet **meddelandestatus** väljer du **Förberedd**. I fältet **svarstyp** anger du **har körts**.

4. Skapa en åtgärd med namnet **Generera rapport** och ange följande fält:

    - På snabbfliken **allmänna** i fältet **åtgärdstyp** väljer du **Export av elektronisk rapportering**. I fältet **Formatmappning**, markera exporterande ER-formatet. Alternativen är **Excel**, **XML**, **JSON**, **Text** och **Andra**.
    - På snabbfliken **Ursprunglig status** i fältet **meddelandestatus** väljer du **Förberedd**.
    - På snabbfliken **Resultatstatus** i fältet **meddelandestatus** väljer du **Genererad**. I fältet **svarstyp** anger du **har körts**.

    ![Åtgärden Generera rapport](media/generate-report-action.png)

5. Valfritt: För att låta användarna generera en rapport om flera gånger kan du skapa en åtgärd kallad **Uppdatera till ursprunglig status** och ange följande fält:

    - På snabbfliken **allmänna** i fältet **åtgärdstyp** väljer du **Användares bearbetning på meddelandenivå**.
    - På snabbfliken **ursprungliga statusar** i fältet **meddelandestatus** väljer du **Genererad**.
    - På snabbfliken **Resultatstatus** lägger du till en separat rad för var och en av två statusvärden för meddelande (**Förberett** och **Nytt**). För båda raderna anger du fältet **svarstyp** till **har körts**.

## <a name="electronic-message-processing"></a>Elektronisk meddelandebearbetning

I det här exemplet ska alla åtgärder konfigureras så att de körs separat. Förutsättningen är att användaren initierar varje åtgärd.

1. Gå till **Skatt** \> **Konfiguration** \> **Elektroniska meddelanden** \> **bearbetning av elektroniska meddelanden**.
2. Lägg till en post för din bearbetning och lägg till alla tidigare definierade åtgärder och ett ytterligare fält.
3. Valfritt: På snabbfliken **säkerhetsroller**, definiera säkerhetsroller för din bearbetning för att begränsa åtkomsten till särskild rapportering.
4. Gå till **Skatt** \> **Förfrågningar och rapporter** \> **Elektroniska meddelanden** \> **Elektroniska meddelanden**.
5. Välj **Ny** för att skapa ett meddelande. Nu kan du lägga till datum och en beskrivning. Du kan också uppdatera värdet för ytterligare fält som du behöver.

    ![Skapa ett elektroniskt meddelande](media/create-electronic-message.png)

    Rutnätet på snabbfliken **Åtgärdslogg** fylls i automatiskt med en logg över alla åtgärder som utförs på meddelandet.

    Du kan nu ta bort eller uppdatera meddelandestatusen. 

6. För att uppdatera meddelandestatus, välj **uppdateringsstatus**. I fältet **ny status** väljer du **förberett** och väljer sedan **OK**.

    ![Uppdatera meddelandets status](media/update-status.png)

    Meddelandestatusen uppdateras till **Förberedd**.

7. Välj **Generera rapport** om du vill generera rapporten.

    Rapporten genereras och meddelandestatus och åtgärdsloggen uppdateras.

8. För att visa den genererade rapporten väljer du knappen **Bilaga** (gemsymbolen) i övre högra hörnet på sidan.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
