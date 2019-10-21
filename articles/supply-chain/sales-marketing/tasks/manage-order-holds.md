---
title: Hantera orderspärrar
description: Denna procedur visar hur du spärrar kundförsäljningsorder, hur du arbetar med utcheckning av spärrade order, samt hur du tar bort orderspärrar.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7168d13ef0b24d06aa28fbbc22bbb4e6093df24
ms.sourcegitcommit: 58db26b7edf02e7c33aaaf1c934e3263aa74b01f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/11/2019
ms.locfileid: "1994920"
---
# <a name="manage-order-holds"></a>Hantera orderspärrar

[!include [task guide banner](../../includes/task-guide-banner.md)]

Denna procedur visar hur du spärrar kundförsäljningsorder, hur du arbetar med utcheckning av spärrade order, samt hur du tar bort orderspärrar. En order kan spärras av flera olika orsaker. Du kan till exempel hålla en order tills en kundadress eller betalningsmetod kan bekräftas eller tills en chef kan granska kundens kreditgräns. En spärrad order kan inte behandlas av lagerstället för transport. 

Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.


## <a name="set-up-order-holds"></a>Ställ in orderspärrar
1. Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Inställningar > Försäljningsorder > Koder för spärrad order**.
2. Klicka på **Ny**.
3. Ange ett värde i fältet **Spärrkod**. Skriv till exempel "Ring tillbaka".  
4. I fältet **Beskrivning** anger du ett värde.
    - Till exempel spärrad order som inväntar att kunden ringer tillbaka.  
    - Du kan också markera kryssrutan **Ta bort reservationer** för att ta bort alla fysiska reservationer från ordern när spärrkoden läggs till.  
5. Klicka på **Spara**.

## <a name="place-order-on-hold"></a>Spärra order
1. Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.
2. Klicka på **Ny**.
3. Ange eller välj ett värde i fältet **Kundkonto**.
4. Klicka på **OK**.
5. I fältet **artikelnummer** anger du eller väljer ett värde.
6. Ange ett nummer i fältet **Kvantitet**.
7. I **åtgärdsrutan**, klicka på **Försäljningsorder**.
8. Klicka på **Spärrade order**.
9. Klicka på **Ny**.
10. Välj den kod som du har skapat i föregående underaktivitet i kodfältet **Spärrkod**.
11. Klicka på **Spara**.
12. Stäng sidan.
13. Gå till **försäljning och marknadsföring > beställningar > alla försäljningsorder**.
14. Markera vald rad i listan. För spärrade order markeras fälten "Behandla inte" och "Spärrad".
15. I åtgärdsrutan, klicka **Plocka och packa**.

## <a name="manage-order-holds"></a>Hantera orderspärrar
1. Gå till **Försäljning och marknadsföring > Försäljningsorder > Öppna order > Spärrade order**. Sidfunktionerna för **spärrad order** fungerar som en arbetsyta, där du kan få en översikt över alla aktuella och bearbetade spärrningar och hantera dem samt tillhörande försäljningsorder.     
2. Markera vald rad i listan.
3. Klicka på **Frisläpp spärr** i **åtgärdsfönstret**.
4. Klicka på **Frisläpp**.
5. Avmarkera vald rad i listan. Fältet **Frisläpp till** anger nu ditt användar-ID.   
6. Klicka på **Rensa frisläpp**.
7. Klicka på **Rensa spärr** i **åtgärdsfönstret**.
    - När du vill ta bort spärren och tillåta att ordern går vidare till nästa steg, måste du rensa spärren. Du kan köra åtgärden Rensa spärrar om ordern inte kräver några ändringar. Om ordern måste uppdateras kan du emellertid använda åtgärden Rensa och ändra när du rensar en spärr.      
    - Åtgärden **Rensa och skicka in** gäller endast när du använder kundtjänstfunktionerna.  
8. Klicka på **Rensa spärrar**. Spärren har nu tagits bort från ordern och från listan över aktiva spärrningar. Ändra värdet i fältet Visa för att visa samtliga spärrningar eller deras underuppsättningar enligt en viss status.     

