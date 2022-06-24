---
title: Power BI-innehåll för prenumerationsfakturering
description: Den här artikeln beskriver vad som ingår i Microsoft Power BI-innehållet för prenumerationsfakturering.
author: JodiChristiansen
ms.date: 04/13/2022
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-04-13
ms.openlocfilehash: 6cee01eb5b8bb8296b6e7f638b565c999ccc023e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849972"
---
# <a name="subscription-billing-power-bi-content"></a>Power BI-innehåll för prenumerationsfakturering

[!include[banner](../includes/banner.md)]

Den här artikeln beskriver vad som ingår i Microsoft Power BI-innehållet för prenumerationsfakturering. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet. 

## <a name="overview"></a>Översikt

I Power BI-innehållet för prenumerationsfakturering har skapats för faktureringsansvarig personal och chefer. Det ger nyckelvärden för abonnemangsfakturering, till exempel månad återkommande intäkt (MRR) för faktureringsscheman, och den degresserande balansen och balansen mellan scheman. Data från faktureringsscheman och de debiteringsscheman används för att ge en översikt över återkommande inkomst och intäkter.

Innehållet Power BI har följande tre flikar som innehåller sammanlagt fyra analysrapporter: 

- **Analys - MRR** – På den här fliken visas rapporten **Månatlig återkommande fakturering** samt informationsrapporten om **Information om fakturaschema**.
- **Analys - Vattenfall** – Denna flik ger rapporten **Vattenfall för intäkter**.
- **Analys – Degressiv avskrivning** – På den här fliken visas rapporten **Degressiv avskrivning**.

## <a name="view-data-on-the-analytical-reports"></a>Visa data i analysrapporterna

Innan du kan visa data i analysrapporterna måste du köra en periodisk process som genererar rapporteringsdata för varje rapport. Dessa data som rapporterna kräver måste genereras eftersom de inte lagras direkt i databasen. 

1. Gå till **Prenumerationsfakturering \> Återkommande kontraktsfakturering \> Periodiska uppgifter \> MRR analytisk rapport batchbearbetning** och följ dessa steg:

    1. Ange ett datumintervall på högst tre år.
    2. Valfritt: Ställ in ett återkommande batchprocessjobb så att data uppdateras regelbundet.
    3. Välj **OK**.

2. När batchjobbet har körts går du till **Systemadministration \> Inställning \> Enhetslagring** och uppdatera **MRR-rapport** sammanlagda mått. 
3. Gå till **Prenumerationsfakturering \> Periodisering av intäkt och utgift \> Periodiska uppgifter \> Batchbearbetning av vattenfallsanalysrapport** och följ dessa steg:

    1. Ange ett startdatum och ett slutdatum som inte omfattar fler än 26 perioder. 
    2. Om du vill visa det prognostiserade beloppet för tidigare perioder i den aktuella perioden ställer du in alternativet **Prognostiserade tidigare belopp under innevarande period** på **Ja**.
    3. Valfritt: Ställ in ett återkommande batchprocessjobb så att data uppdateras regelbundet.
    4. Välj **OK**. 

4. När batchjobbet har körts går du till **Systemadministration \> Inställning \> Enhetslagring** och uppdatera **Vattenfallrapport** sammanlagda mått.
5. Gå till **Prenumerationsfakturering \> Periodisering av intäkt och utgift \> Periodiska uppgifter \> Batchbearbetning av analysrapport för degressiv avskrivning** och följ dessa steg:

    1. Ange ett startdatum och ett slutdatum som inte omfattar fler än 26 perioder. 
    2. Om du vill visa det prognostiserade beloppet för tidigare perioder i den aktuella perioden ställer du in alternativet **Prognostiserade tidigare belopp under innevarande period** på **Ja**.
    3. Valfritt: Ställ in ett återkommande batchprocessjobb så att data uppdateras regelbundet.
    4. Välj **OK**.

6. När batchjobbet har körts går du till **Systemadministration \> Inställning \> Enhetslagring** och uppdatera **Rapport för degressiv avskrivning** sammanlagda mått.

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll

Prenumerationsfakturering Power BI-innehåll visas i arbetsytan **Prenumerationsfakturering**.
