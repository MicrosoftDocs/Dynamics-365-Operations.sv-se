---
title: Projektanslag
description: Det här ämnet förklarar hur du skapar eller ändrar ett anslag.
author: RadhikaRS
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: f4f7d347dab9f02fc474656e2f4cfba8e374480d
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282850"
---
# <a name="project-grants"></a>Projektanslag

[!include [banner](../includes/banner.md)]

Ett anslag är en gåva av pengar för ett visst syfte eller projekt. Vanligtvis finns det begränsningar på hur ett anslag kan använts. I Projekthantering och redovisning kan du ange och spåra anslag och definiera deras relationer till projekt och projektkontrakt. Du kan till exempel utföra följande uppgifter:

- Associera bidrag med projekt och finansieringskällor via länkar till sidorna **projekt** och **projektkontraktsinformation**.
- Ange och spåra ändringar i ett anslag som flyttar från en status till en annan.
- Ange och spåra kostnader, begärda tilldelade belopp och belopp.
- Skapa huvudanslag och koppla delanslag med dem.

Du kan skapa ett anslag genom att ange alla detaljer till den nya posten, eller så kan du kopiera informationen från ett befintligt anslag och sedan uppdatera den.

## <a name="create-a-new-grant"></a>Skapa ett nytt anslag

1. Gå till **Projekthantering och redovisning** \> **Anslag** \> **Anslag**.
2. Välj **Ny** \> **Anslag**.
3. På sidan anslagsinformation, på snabbfliken **Allmänt** i fältet **anslags-ID** anger du en alfanumerisk identifierare för anslaget.
4. I fältet **anslagsnamn** anger du ett namn för anslaget.
5. I fältet **Beskrivning** lägger du till information om det nya anslaget.

    De flesta av de andra fälten på sidan är valfria, och du kan ange lite eller så mycket information, som du vill ha.

    I följande lista beskrivs den information som anges på varje snabbflik på sidan beviljande av information:

    - **Allmänt** – Ange anslagets namn, status, beskrivning, syfte och belopp.
    - **Kontaktinformation** – Ange information om anställda, den avdelning som hanterar anslaget och anslagskunden eller organisationskällan för anslaget. Du kan också ange om din organisation är en mellanhand som tar emot anslaget och sedan passar det vidare till en annan mottagare. Välj **Lägg till** om du vill lägga till kontaktinformation till exempel telefonnummer och e-postadresser för företaget som tillhandahåller anslaget.
    - **Datum och deadlines** – Ange datum som är relaterade till anslaget och bevilja den till programmet. Exempel på detta är förfallodatum för ansökan, överföringsdatum och det datum då anslaget godkänns eller avvisas.
    - **Associerade projekt och projektkontrakt** – du kan bara ange information på den här snabbfliken om fältet **anslagets status** på snabbfliken **allmänt** är inställt på **aktiv** eller **beviljad**. Välj bland följande alternativ för att slutföra den relaterade uppgiften:

        - **Lägg till finansieringskällor** – Lägg till en ny finansieringskälla för anslaget. Du kan ange all information nu, eller du kan använda standardinformation och uppdatera dem senare.
        - **Lägg till projektkontrakt** – Lägg till eller uppdatera information om projektkontrakt.
        - **Lägg till projekt** – Lägg till eller uppdatera projektinformation.

    - **Inställningar** – ange information om matchande medel, om den här informationen behövs. Många organisationer som tilldelar anslag kräver att den mottagaren spendera en viss summa av sina egna pengar eller resurser som matchar det belopp som används i anslaget. I fältet **lokalt projekt eller spårnings-ID** kan du ange en identifierare som skiljer sig från projektidentifieraren.

        > [!NOTE]
        > Om en del av anslaget kommer att tilldelas en annan organisation, ange alternativet **Delöverlåtare** till **Ja**. För anslag som tilldelas i USA kan du ange om ett anslag tilldelas under en delstat eller federal fullmakt.

    - **Neddragna detaljer** – Lägg till eller uppdatera information om hur ofta, anslag kan tas ut, faktureras eller spenderas.

## <a name="create-a-new-grant-from-a-copy"></a>Skapa ett nytt anslag från en kopia

1. Gå till **Projekthantering och redovisning** \> **Anslag** \> **Anslag**.
2. Välj **Ny** \> **kopia från anslag**.
3. Ange en alfanumerisk identifierare och ett namn för det nya anslaget och klicka sedan på **OK**.
4. Granska informationen för det kopierade anslaget på sidan med anslagsinformation och gör de ändringar som behövs. De flesta fälten på sidan är valfria.

## <a name="view-or-modify-grant-details"></a>Visa eller ändra anslagsdetaljer

1. Gå till **Projekthantering och redovisning** \> **Anslag** \> **Anslag**.
2. Välj det anslag du vill ändra.
3. I Åtgärdsfönstret, på fliken **anslag**, i gruppen **underhåll**, markerar du **redigera**.
4. Granska anslagsdetaljerna och gör nödvändiga ändringar.
