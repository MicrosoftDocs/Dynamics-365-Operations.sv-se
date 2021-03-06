---
title: Underhållsstatus
description: I det här avsnittet beskrivs hur du beräknar underhållsstatus i Tillgångshantering.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetStatusCalculate, EntAssetStatus
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f3d6f86c5052c845c9c8aad1e4437f4196f78b50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808626"
---
# <a name="maintenance-status"></a>Underhållsstatus

[!include [banner](../../includes/banner.md)]

 

I Tillgångshantering kan du göra en översiktsberäkning för en viss period för nya, aktiva och slutförda underhållsbegäranden, arbetsorder och underhållsstopp. Du kan också se antalet slutförda tillståndsbedömningar för samma period. Använd beräkningen för att få en översikt över arbetsbelastningen för inkommande och slutförda underhållsbegäranden och arbetsorder.

## <a name="make-a-maintenance-status-calculation"></a>Göra en beräkning av underhållsstatus

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Underhållsstatus**.

2. I dialogrutan **Beräkna status**, välj det tidsintervall för vilket du vill utföra beräkningen i fälten **Från datum** och **Till datum**.

3. Du kan använda fältet **Nivå** för att indikera hur detaljerade underhållsraderna ska vara gällande funktionsplatser. 

  Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsrader för en funktionsplats på den översta nivån, och därmed kan också den status som finns på en rad läggas till från funktionsplatser på en lägre nivå. 
  
  Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsrader på alla de funktionsplatsnivåer som de är relaterade till.

4. Klicka på **OK** för att starta beräkningen.

5. Klicka på knapparna **Gruppera efter...** för att visa den obligatoriska detaljnivån för beräkningen. De valda knapparna **Gruppera efter** markeras. Klicka på en knapp för att aktivera och inaktivera den.

6. Kom ihåg att klicka på knapparna **Uppdatera** om du vill uppdatera beräkningen varje gång du gör ändringar genom att aktivera eller inaktiverar knapparna **Gruppera efter** eller genom att göra en beräkning för en ny period.

7. Klicka på **Status** om du vill skapa en ny underhållsstatusberäkning.

>[!NOTE]
>Resultaten som visas i **Underhållsstatus** omfattar bara underhållsbegäranden och arbetsorder som har ett faktiskt startdatum och en faktisk starttid. Slutdatum och sluttid kan vara tomma.

## <a name="example-1"></a>Exempel 1

I bildskärmen nedan har knapparna **År** och **Månad** aktiverats. Med dessa val för **Gruppera efter** markerade får du en allmän översikt på basis av månadsvis arbetsbelastning och genomflöde som är relaterat till underhållsbegäranden och arbetsorder. 

![Exempel på månatlig arbetsbelastning](media/13-controlling-and-reporting.png)

## <a name="example-2"></a>Exempel 2

I bildskärmen nedan har information om funktionsplatser lagts till. Nu är det möjligt att jämföra arbetsbelastning och genomflöde på funktionsplatser, vilket kan representera geografiska platser, fabriker eller arbetsområden. 

![Exempel på en månatlig arbetsbörda med funktionella platser](media/14-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]