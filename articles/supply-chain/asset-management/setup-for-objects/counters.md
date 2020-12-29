---
title: Tillgångsmått
description: Det här avsnittet beskriver hur du skapar tillgångsmåttyper i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCounterPart, EntAssetObjectCounterLookup, EntAssetCounterType, EntAssetObjectCounterTotals
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: adadb1df7b41488fad496f937ecbc24e0761e42d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437776"
---
# <a name="counters"></a>Räknare

[!include [banner](../../includes/banner.md)]

Det här avsnittet beskriver hur du skapar räknartyper i tillgångshantering. Räknartyper används för att göra räknarregistreringar på tillgångar, till exempel om antalet produktionstimmar eller kvantiteten som produceras på tillgången. tillgångstyper är relaterade till räknartyperna. Det innebär att en räknare endast kan användas på en tillgång om räknaren ställs in på den tillgångstyp som används på tillgången.

Innan du kan göra räknarregistreringar på tillgångar skapar du först de räknartyper som du vill använda i **räknare**. Därefter kan du skapa räknarregistreringar för tillgångar i **räknare**. 

Räknare kan användas i underhållsplaner. En underhållsplanrad kan vara av typen "räknare", till exempel när det gäller antalet produktionstimmar eller producerade kvantiteter. 

En räknarregistrering kan uppdateras manuellt eller automatiskt baserat på produktionstimmar eller producerad kvantitet. En räknare kan ställas in för att använda en av tre uppdateringsmetoder (vald i fältet **uppdatera** i **räknare**):
  
- Manuell - du måste registrera värden för räknare manuellt.  
- Produktionstimmar - räknaren uppdateras automatiskt baserat på antalet produktionstimmar.  
- Produktionskvantitet - räknaren uppdateras automatiskt baserat på antalet producerad kvantitet.  

>[!NOTE]
>Om den producerade kvantiteten används inkluderas *alla* registrerade artiklar i räknarregistreringen, god kvantitet samt felkvantitet. Det är alltid möjligt att göra manuella räknarregistreringar, om det behövs.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Skapa räknartyper för tillgångsräknarregistreringar

1. Välj **tillgångshantering** > **inställningar** > **tillgångstyper** > **räknare**.
2. Skapa en ny räknartyp genom att välja **Nytt**.
3. Infoga ett ID i fältet **räknare** och ett räknarnamn i fältet **namn**.
4. På snabbfliken **Allmänt** väljer du räknarenhet i fältet **enhet**.
5. I fältet **uppdatera** väljer du den uppdateringsmetod som ska användas för räknare.
6. Välj "Ja" på växlingsknappen **Ärva räknarvärden** om underordnade tillgångar i en tillgångsstruktur automatiskt ska ärva räknarregistreringar som gjorts på den överordnade tillgången.
7. I fältet **total sammanlagd** väljer du den summeringsmetod som ska användas för en räknare med den här räknartypen. "Summa" är det standardval som används för att kontinuerligt lägga till registrerade värden till det totala värdet. "Genomsnitt" kan användas om en räknare har ställts in för att övervaka ett tröskelvärde, till exempel när det gäller temperatur, vibrationer eller slitage på en tillgång. 
8. I fältet **avvikelse över** infogar du den övre nivån i procent för validering om manuella räknarregistreringar ligger inom ett förväntat intervall. Valideringen baseras på en linjär ökning av befintliga räknarregistreringar.
9. I fältet **avvikelse under** infogar du den nedre nivån i procent för validering om manuella räknarregistreringar ligger inom ett förväntat intervall. Valideringen baseras på en linjär minska av befintliga räknarregistreringar.
10. I fältet **typ** väljer du den typ av meddelande (information, varning, fel) som ska visas om avvikelser utanför det definierade intervallet inträffar när du gör manuella räknarregistreringar.
11. På snabbfliken **tillgångstyper** lägger du till de tillgångstyper som ska kunna använda räknare.
12. På snabbfliken **relaterade tillgångsräknare** lägger du till de räknare som du vill ska uppdateras automatiskt när den här räknaren uppdateras.


>[!NOTE]
>En relaterad räknare uppdateras automatiskt endast om den relaterade räknaren har tillgångstypen, till vilken den är relaterad, i inställningarna för räknare. Exempel: du ställer in en räknare för "produktionstimmar" och lägger till tillgångstypen "lastbilsmotor". När den räknaren uppdateras kommer även en relaterad räknare "olja" att uppdateras med samma värden för räknare. Inställningen i **räknare** innehåller inställningarna på "timmar". På räknaren "Olja" bör "lastbilsmotor" läggas till på snabbfliken **tillgångstyper** för att säkerställa räknarrelationen. Se skärmdumparna nedan för ett exempel på inställningen på räknarna timmar och olja.

När tillgångstyper läggs till en räknartyp i **räknare**, läggs den räknaren automatiskt till tillgångstyperna på snabbfliken **räknare** i [tillgångstyper](../setup-for-objects/object-types.md).

![Figur 1](media/071-setup-for-objects.png)

