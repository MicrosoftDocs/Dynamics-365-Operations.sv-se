---
title: 'Definiera rullande inventering '
description: Rullande inventering är en lagerställesprocess som du kan använda för att kontrollera lagerbehållningsartiklar.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8b7f39fc9a91d9fe219445e409d000266e24775
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016158"
---
# <a name="define-cycle-counting"></a>Definiera rullande inventering  

[!include [banner](../../includes/banner.md)]

Rullande inventering är en lagerställesprocess som du kan använda för att kontrollera lagerbehållningsartiklar. Den här uppgiftsinspelningen visar hur du kan ställa in standardarbetsprioriteten för inventering; aktivera ett menykommando för mobila enheter för att bearbeta både plocknings- och inventeringsåtgärder; aktivera en utlösare för inventeringströskeln när en plats blir tom; aktivera en plan för rullande inventering för en viss artikel i ett bestämt lagerställe. Dessa inställningsuppgifter utförs normalt av en lagerchef. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller i dina egna data.


## <a name="set-the-priority-of-counting-work"></a>Ange prioriteten för inventeringsarbete
1. I **Navigeringsfönster** gå till **Moduler > Lagerstyrning > Inställningar > Parametrar för lagerstyrning**.
2. Klicka på fliken **Rullande inventering**.
3. Ange ett värde i fältet **Standardarbetsprioritet för rullande inventering**. Det här steget ändrar prioriteten för arbetet med rullande inventering jämfört med andra typer av arbete i lagerstället. Genom att ange ett lägre nummer än numret för andra typer av arbete, ger du arbetet med rullande inventering en högre prioritet.  
4. Klicka på **Spara**.
5. Stäng sidan.

## <a name="enable-the-mobile-device"></a>Aktivera den mobila enheten
1. I **Navigeringsfönster** , gå till **Moduler > Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet**.
2. Klicka på **Ny**.
3. Ange ett värde i fältet **Menyalternativnamn**.
4. Ange ett värde i fältet **Rubrik**.
5. Välj Arbete i fältet **Läge**.
6. Ange alternativet **Använd befintligt arbete** till Ja. Om du anger det här alternativet till Ja kommer systemet att leta efter befintligt arbete när menykommandot för mobila enheter används.  
7. Välj Systemstyrd i fältet **Dirigerad av**. När Systemstyrd har valts styrs lagerarbetaren till öppet arbete som definieras i arbetsklasser. (Vi ska skapa dessa arbetsklasser härnäst.)  
8. Expandera snabbfliken **Arbetsklasser**. Härnäst ska vi skapa två arbetsklasser som ska användas med menykommandot för mobila enheter. När menykommandot används skickas frågor till dessa arbetsklasser, och arbetet med den högsta prioriteten visas för användaren.  
9. Klicka på **Ny**.
10. Välj ett värde i fältet **Arbetsklass-ID**.
11. Klicka på **Ny**.
12. Välj ett värde i fältet **Arbetsklass-ID**.
13. I **åtgärdsfönstret** , klicka på **Spara**.
14. Stäng sidan.
15. I **Navigeringsfönster** , gå till **Moduler > Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet**.
16. Hitta och markera önskad post i listan.
17. Välj menykommandot som du nyss skapat i trädet.
18. Klicka på **Redigera**.
19. Klicka på pilen för att lägga till menykommandot på menyn.
20. Klicka på **Spara**.

## <a name="create-a-counting-threshold"></a>Skapa en tröskel för rullande inventering
1. I **navigeringsfönster** , gå till **Moduler > Lagerstyrning > Inställningar > Rullande inventering > Trösklar för rullande inventering**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Tröskel-ID för rullande inventering**.
4. Ange alternativet **Bearbeta rullande inventering direkt** till Ja.
5. I fältet **Beskrivning** anger du ett värde.
6. Klicka på **Spara**.
7. Klicka på **Välj platser**.
8. Markera vald rad i listan.
9. Välj ett värde i fältet **Kriterier**.
10. Klicka på **OK**.
11. Stäng sidan.

## <a name="create-a-cycle-count-plan"></a>Skapa en plan för rullande inventering
1. I **navigeringsfönster** , gå till **Moduler > Lagerstyrning > Inställningar > Rullande inventering > Planer för rullande inventering**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Plan-ID för rullande inventering**.
4. I fältet **Beskrivning** anger du ett värde.
5. Ange ett värde i fältet **Högsta antal rullande inventeringar**.
6. Klicka på **Spara**.
7. Klicka på **Välj platser**.
8. Markera vald rad i listan.
9. Välj ett värde i fältet **Kriterier**.
10. Klicka på **OK**.
11. Ange ett värde i fältet **Dagar mellan rullande inventering**. Om till exempel fältet **Dagar mellan rullande inventering** anges till 5 kommer ett arbete för rullande inventering att skapas var femte dag. Men om arbete för rullande inventering bearbetas på dag tre kommer nästa arbete för rullande inventering skapas fem dagar efter att den sista rullande inventeringen bearbetades på dag åtta.  
12. Klicka på **Spara**.
13. Klicka på **Ny**.
14. Ange ett nummer i fältet **Sekvensnummer**. Sorteringsordningen är från det lägsta talet till det högsta talet. Värdet måste vara större än 0 (noll).  
15. Markera vald rad i listan.
16. I fältet **Beskrivning** anger du ett värde.
17. Klicka på **Spara**.
18. Klicka på frågan **Definiera produkt**.
19. Markera vald rad i listan.
20. I fältet **Kriterier** anger du eller väljer ett värde.
21. Klicka på **OK**.
22. Stäng sidan.

