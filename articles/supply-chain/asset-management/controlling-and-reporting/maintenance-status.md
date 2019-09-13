---
title: Underhållsstatus
description: I det här avsnittet beskrivs hur du beräknar underhållsstatus i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 516607c056125a16e075c33f3c2ad069efb396d9
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918359"
---
# <a name="maintenance-status"></a>Underhållsstatus

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I Tillgångshantering kan du göra en beräkning som visar en översikt över nya, aktiva och slutförda underhållsbegäranden, arbetsorder och underhållsstopp för en viss period. Du kan också se antalet slutförda tillståndsbedömningar för samma period. Använd beräkningen för att få en översikt över arbetsbelastningen på inkommande och slutförda underhållsbegäranden och arbetsorder.

## <a name="make-a-maintenance-status-calculation"></a>Göra en beräkning av underhållsstatus

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Underhållsstatus**.

2. I dialogrutan **Beräkna status**, välj den period för vilken du vill utföra beräkningen i fälten **Från datum** och **Till datum**.

3. Du kan använda fältet **Nivå** för att indikera hur detaljerade underhållsraderna ska vara gällande funktionsplatser. Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsrader för en funktionsplats på den översta nivån, och därmed kan också den status som finns på en rad läggas till från funktionsplatser på en lägre nivå. Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsrader på alla de funktionsplatsnivåer som de är relaterade till.

4. Klicka på **OK** för att starta beräkningen.

5. I **Gruppera efter...**-åtgärdsfönstergrupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna i åtgärdsfönstret markeras. Klicka på en knapp för att aktivera och inaktivera den.

6. Kom ihåg att klicka **Uppdatera** om du vill uppdatera beräkningen varje gång du gör ändringar genom att aktivera eller inaktiverar **Gruppera efter...**-knappar eller genom att göra en beräkning för en ny period.

7. Klicka på **Status** om du vill skapa en ny underhållsstatusberäkning.

>[!NOTE]
>Resultaten som visas i **Underhållsstatus** omfattar bara underhållsbegäranden och arbetsorder som har ett faktiskt startdatum och en faktisk starttid. Slutdatum och sluttid kan vara tomma.

*Exempel 1:*

I bilden nedan har knapparna **År** och **Månad** aktiverats. Här får du en allmän översikt på basis av månadsvis arbetsbelastning och genomflöde som är relaterat till underhållsbegäranden och arbetsorder. 

![Figur 1](media/13-controlling-and-reporting.png)

*Exempel 2:*

I bilden nedan har information om funktionsplatser lagts till. Nu är det möjligt att jämföra arbetsbelastning och genomflöde på funktionsplatser, vilket kan representera geografiska platser, fabriker eller arbetsområden. 

![Figur 2](media/14-controlling-and-reporting.png)

