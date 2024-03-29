---
title: Godkännandearbetsflöden för lagerjournal
description: Denna artikel ger en beskrivning av hur du kan konfigurera och använda arbetsflöden för lagerjournaler för olika typer av fysiska lagertransaktioner. Arbetsflöden för lagerjournal hjälper till att säkerställa att endast godkända lagerjournaler kan bokföras på transaktioner.
author: yufeihuang
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTableWorkflowDropDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3a97eaeae24850282c39196a61e3baa29307aa93
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334668"
---
# <a name="inventory-journal-approval-workflows"></a>Godkännandearbetsflöden för lagerjournal

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur man konfigurerar och använder arbetsflöden för godkännande av lagerjournal för olika typer av fysiska inventeringstransaktioner, såsom emissioner och kvitton, lagerrörelser, strukturlistor (BOM) och avstämning av fysisk inventering. Arbetsflöden för lagerjournal hjälper till att säkerställa att endast godkända lagerjournaler kan bokföras på transaktioner.

> [!NOTE]
> Arbetsflöden för godkännande av lagerjournal gäller bara för transaktioner som registrerats med modulen lagerhantering. De fungerar inte med lagerjournaler som aktiverats från modulen för lagerstyrning.

## <a name="turn-the-inventory-journal-approval-workflows-feature-on-or-off"></a>Aktivera eller inaktivera funktionen godkännandearbetsflöden för lagerjournal

Innan du kan använda funktionen måste den aktiveras i ditt system. Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.29 version av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.29 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Godkännandearbetsflöde för lagerjournal* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="create-your-inventory-journal-approval-workflows"></a>Skapa ditt godkännandearbetsflöde för lagerjournal

Om du vill konfigurera den här funktionen måste du skapa ett arbetsflöde för varje typ av lagerjournal som du vill styra. Eftersom olika typer av lagerjournaler kan ha olika godkännandehierarkier och arbetsflödessteg kan du konfigurera enskilda arbetsflöden för varje lagerjournaltyp.

Arbetsflöden stöder versionskontroll och var och en har ett arbetsflödes-ID och en aktiv version. Du kan välja att aktivera varje ny arbetsflödesversion direkt när du har skapat den eller behålla den inaktiv. Om du behöver olika arbetsflöden för samma journaltyp skapar du flera arbetsflöden för journaltypen och tilldelar sedan var och en av dessa till ett annat journalnamn som använder den typen.

För att skapa ditt godkännandearbetsflöde för lagerjournal:

1. Gå till **Lagerhantering \> Inställningar\> Arbetsflöden för lagerhantering**.
1. Välj **Ny** i åtgärdsfönstret.
1. Välj den typ av lagerjournal för vilken du vill konfigurera ett arbetsflöde:
    - **Journal för lagermärkesinventering**
    - **Journal för lagerägarskapsändring**
    - **Lagerrörelsejournal**
    - **Lageröverföringsjournal**
    - **Lagerinventeringsjournal**
    - **Lagerjournal för strukturlista**
    - **Lagerjusteringsjournal**

    ![Dialogrutan skapa arbetsflöde.](media/journal-workflow-create-workflow.png "Dialogrutan skapa arbetsflöde")

1. Arbetsflödesredigerarens app startas på din dator. (Du kan bli ombedd att godkänna den här åtgärden.) Använd den för att utforma arbetsflödet efter behov. Mer information om hur du använder arbetsflödes redigeraren finns i [arbetsflödessystem – översikt](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).
1. När du har sparat och stängt appen i arbetsflödes redigeraren måste du välja om du vill aktivera arbetsflödesversionen eller behålla den som inaktiv.

> [!NOTE]
> Arbetsflöden innehåller versionskontroll, vilket innebär att du kan visa en lista med versioner som du har skapat och välja vilken av dem som är aktiva. Om du vill visa listan med tillgängliga versioner och välja vilken du vill aktivera väljer du ett arbetsflöde i listan på sidan **arbetsflöden för lagerhantering**. Öppna fliken arbetsflöde i åtgärdsfönstret **Arbetsflöden** och välj **versioner**. Endast en version kan vara aktiv åt gången för varje arbetsflödes-ID.

## <a name="assign-approval-workflows-to-inventory-journal-names"></a>Tilldela godkännandearbetsflöden för lagerjournalnamn

Nästa steg är att tilldela ett arbetsflöde för lagerjournal till varje lagerjournalnamn. För varje lagerjournaltyp kan du konfigurera flera namn på lagerjournaler.

Så här kopplar du ett arbetsflöde för lagerjournal med ett lagerjournalnamn:

1. Gå till **Lagerhantering \> Inställningar \> Journalnamn \> Lager**.
1. Välj ett journalnamn från listkolumnen för att öppna sidan inställningar för dess inställningar.
1. På snabbfliken **Allmänt** ställer du in **Godkännandearbetsflöde** till **Ja**. Om du uppmanas att bekräfta åtgärden väljer du **Ja**.

    ![Tilldela ett arbetsflöde till ett journalnamn.](media/journal-workflow-journal-name.png "Tilldela ett arbetsflöde till ett journalnamn")

1. Öppna listrutan **Arbetsflöde** och välj lämpligt arbetsflöde. I listan visas varje aktivt arbetsflöde som du har skapat med hjälp av appen arbetsflödesredigeraren.

## <a name="create-an-inventory-journal-and-send-it-for-approval"></a>Skapa en lagerjournal och skicka den för godkännande

När du har associerat namnet på en lagerjournal med det matchande arbetsflödet för godkännande av lagerjournal kan du skapa nya lagerjournaler som använder det namnet och sedan skicka dessa journaler för godkännande med hjälp av det arbetsflödet. Du kan inte bokföra lagerjournalen förrän den har godkänts av godkännaren som konfigurerats i arbetsflödet.

1. I navigeringsfönstret, expandera **Lagerhantering \> Journalposter \> Artiklar** och välj sedan en lagerjournaltyp.
1. Välj **ny** om du vill skapa en ny journal av den valda typen.
1. Dialogrutan **Skapa lagerjournal** öppnas. Fyll i formuläret efter behov och välj sedan **OK** för att spara journalen.
1. Fyll i journalen efter behov.
1. När du skapar eller öppnar en lagerjournal med ett godkännande arbetsflöde som är associerat med den, kommer knappen **arbetsflöde** att vara aktiv i åtgärdsfönstret. När du är klar att skicka in journalen för godkännande väljer du knappen **arbetsflöde** för att öppna en nedrullningsbar dialogruta och sedan välja **Skicka**. Godkännandeförfrågan skickas sedan till relevant godkännare, som meddelas med hjälp av den meddelandemetod som har konfigurerats för arbetsflödet.

    ![Skicka en journal för godkännande.](media/journal-workflow-inventory-journal.png "Skicka en journal för godkännande")

Om du vill återkalla en begäran om godkännande öppnar du den relevanta journalen, väljer knappen **Arbetsflöde** och väljer sedan **återkalla**. Detta återställer arbetsflödet.

När journalen har godkänts kan du bokföra den. Om du vill bokföra journalen väljer du **Bokför** i åtgärdsfönstret. Om knappen **Bokför** inte är aktiv har journalen ännu inte godkänts.

## <a name="respond-to-an-inventory-journal-approval-request"></a>Svara på en begäran om godkännande av lagerjournal

Om du är en godkännare ska du få ett meddelande varje gång ditt godkännande behövs (som du har konfigurerat i det relevanta arbetsflödet). Sedan kan du godkänna eller avvisa en begäran om journalgodkännande genom att göra följande:

1. I navigeringsfönstret, expandera **Lagerhantering \> Journalposter \> Artiklar** och välj sedan en lagerjournaltyp.
1. Öppna relevant journal och granska den.
1. Klicka på knappen **arbetsflöde** i åtgärdsfönstret för att öppna en nedrullningsbar dialogruta. Välj en av följande:
    - **Godkänn** – för att godkänna begäran.
    - **Avvisa** – för att avvisa begäran.
    - **Fler \> Begär ändring** – om du vill skicka ett meddelande till en beställare som ber dem att ändra något specifikt och sedan skicka det på nytt.
    - **Fler \> Delegera** – för att delegera godkännandet till en annan användare.
    - **Fler \> Återkalla** – att återkalla godkännandebegäran (återställer arbetsflödet).
    - **Fler \> Arbetsflödeshistorik** – om du vill visa historiken för det här godkännande arbetsflödet hittills.

## <a name="review-the-approval-history"></a>Granska godkännandehistoriken

På samma sätt som andra typer av arbetsflöden kan du använda sidan **arbetsflödeshistorik** om du vill visa historiken för godkännande arbetsflödet för alla journaler.

Så här granskar du arbetsflödeshistoriken för en journal:

1. I navigeringsfönstret, expandera **Lagerhantering \> Journalposter \> Artiklar** och välj sedan en lagerjournaltyp.
1. Öppna relevanta journalen.
1. Klicka på knappen **arbetsflöde** i åtgärdsfönstret för att öppna en nedrullningsbar dialogruta. Välj **arbetsflödeshistorik**. Mer information finns i [Visa arbetsflödeshistorik](../../fin-ops-core/fin-ops/organization-administration/tasks/view-workflow-history.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]