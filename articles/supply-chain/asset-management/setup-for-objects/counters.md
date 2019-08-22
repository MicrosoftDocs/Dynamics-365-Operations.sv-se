---
title: Tillgångsmått
description: Det här avsnittet beskriver hur du skapar tillgångsmåttyper i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c445832a649c4f6a6642036ecab325e8aa2079
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783609"
---
# <a name="asset-measures"></a>Tillgångsmått

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Det här avsnittet beskriver hur du skapar tillgångsmåttyper i tillgångshantering. tillgångsmåttyper används för att göra mätningsregistreringar på tillgångar, till exempel om antalet produktionstimmar eller kvantiteten som produceras på tillgången. tillgångstyper är relaterade till tillgångsmåttyperna. Det innebär att ett tillgångsmått endast kan användas på en tillgång om tillgångsmåttet ställs in på den tillgångstyp som används på tillgången.

Innan du kan göra mätningsregistreringar på tillgångar skapar du först de tillgångsmått typer som du vill använda i **räknare**. Därefter kan du skapa mätningsregistreringar för tillgångar i **tillgångsmått**. 

Tillgångsmått kan användas i underhållsplaner. En underhållsplanrad kan vara av typen "räknare", till exempel när det gäller antalet produktionstimmar eller producerade kvantiteter. 

En tillgångsmätningsregistrering kan uppdateras manuellt eller automatiskt baserat på produktionstimmar eller producerad kvantitet. Ett tillgångsmått kan ställas in för att använda en av tre uppdateringsmetoder (vald i fältet **uppdatera** i **räknare**):
  
- Manuell - du måste registrera värden för tillgångsmått manuellt.  
- Produktionstimmar - räknaren uppdateras automatiskt baserat på antalet produktionstimmar.  
- Produktionskvantitet - räknaren uppdateras automatiskt baserat på antalet producerad kvantitet.  

>[!NOTE]
>Om den producerade kvantiteten används inkluderas *alla* registrerade artiklar i mätningsregistreringen, god kvantitet samt felkvantitet. Det är alltid möjligt att göra manuella tillgångsmätningsregistreringar, om det behövs.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Skapa räknartyper för tillgångsräknarregistreringar

1. Välj **tillgångshantering** > **inställningar** > **tillgångstyper** > **räknare**.
2. Skapa en ny tillgångsmåttyp genom att välja **Nytt**.
3. Infoga ett ID i fältet **räknare** och ett räknarnamn i fältet **namn**.
4. På snabbfliken **Allmänt** väljer du måttenhet i fältet **enhet**.
5. I fältet **uppdatera** väljer du den uppdateringsmetod som ska användas för tillgångsmåttet.
6. Välj "Ja" på växlingsknappen **Ärva räknarvärden** om underordnade tillgångar i en tillgångsstruktur automatiskt ska ärva tillgångsmåttregistreringar som gjorts på den överordnade tillgången.
7. I fältet **total sammanlagd** väljer du den summeringsmetod som ska användas för en tillgångsmått med den här tillgångsmåttypen. "Summa" är det standardval som används för att kontinuerligt lägga till registrerade värden till det totala värdet. "Genomsnitt" kan användas om ett tillgångsmått har ställts in för att övervaka ett tröskelvärde, till exempel när det gäller temperatur, vibrationer eller slitage på en tillgång. 
8. I fältet **avvikelse över** infogar du den övre nivån i procent för validering om manuella tillgångsmåttregistreringar ligger inom ett förväntat intervall. Valideringen baseras på en linjär ökning av befintliga tillgångsmåttregistreringar.
9. I fältet **avvikelse under** infogar du den nedre nivån i procent för validering om manuella tillgångsmåttregistreringar ligger inom ett förväntat intervall. Valideringen baseras på en linjär minskning av befintliga tillgångsmåttregistreringar.
10. I fältet **typ** väljer du den typ av meddelande (information, varning, fel) som ska visas om avvikelser utanför det definierade intervallet inträffar när du gör manuella tillgångsmåttregistreringar.
11. På snabbfliken **tillgångstyper** lägger du till de tillgångstyper som ska kunna använda tillgångsmåttet.
12. På snabbfliken **relaterade tillgångsmått** lägger du till de tillgångsmått som du vill ska uppdateras automatiskt när den här tillgångsmåtten uppdateras.


>[!NOTE]
>Ett relaterat tillgångsmått uppdateras automatiskt endast om det relaterade tillgångsmåttet har tillgångstypen, till vilken den är relaterad, i inställningarna för tillgångsmått. Exempel: du ställer in ett tillgångsmått för "produktionstimmar" och lägger till tillgångstypen "lastbilsmotor". När det tillgångsmåttet uppdateras kommer även en relaterad räknare "olja" att uppdateras med samma värden för tillgångsmått. Inställningen i **räknare** innehåller inställningarna på "timmar". På tillgångsmåttet "Oil" bör tillgångstypen "lastbilsmotor" läggas till på snabbfliken **tillgångstyper** för att säkerställa att tillgångsmåttrelationen. Se skärmdumparna nedan för ett exempel på inställningen på tillgångsmåtten timmar och olja.

När tillgångstyper läggs till en tillgångsmåtttyp i **räknare**, läggs det tillgångsmåttet automatiskt till tillgångstyperna på snabbfliken **räknare** i [tillgångstyper](../setup-for-objects/object-types.md).

![Figur 1](media/071-setup-for-objects.png)


