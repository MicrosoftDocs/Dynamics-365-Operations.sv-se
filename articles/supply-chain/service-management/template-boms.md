---
title: Strukturlistemallar
description: En mallstrukturlista ger dig en standardiserad lista över vilka komponenter i serviceobjekt som regelbundet servas.
author: ShylaThompson
manager: AnnBe
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9c61ecd79f38301f46e3c21a33ec2801f33d19f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "341314"
---
# <a name="template-boms"></a>Strukturlistemallar    

[!include [banner](../includes/banner.md)]


En mallstrukturlista ger dig en standardiserad lista över vilka komponenter i serviceobjekt som regelbundet servas. Komponenterna i mallstrukturlistan representerar de enskilda delkomponenterna i serviceobjektet. När du använder en mallstrukturlista på ett serviceobjekt håller du med hjälp av en servicestrukturlista reda på vilka reservdelar som har ersatts i serviceobjektet.

Om du vill använda en mallstrukturlista på ett serviceavtal eller en serviceorder kopplar du den till en serviceobjektrelation.


> [!NOTE]
> <P>Du kan endast koppla en mallstrukturlista till varje serviceobjekt.</P>

## <a name="create-a-template-bom"></a>Skapa en strukturlistemall

Tabellen nedan innehåller information om de olika metoder som du kan använda för att skapa en mallstrukturlista.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Metod</p></th>
<th><p>beskrivning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Produktion</p></td>
<td><p> Mallstrukturlistan baseras på en tillverkningsorder. Det här alternativet använder du om du arbetar i en tillverkningsmiljö. Fördelen är att du har en aktuell och detaljerad lista över de komponenter som en artikel består av.</p></td>
</tr>
<tr class="even">
<td><p>Artikel BOM</p></td>
<td><p>Mallstrukturlistan baseras på en artikelstrukturlista Artikelstruktur, till skillnad från produktionsstrukturlistan, är en statisk lista över de komponenter som en artikel utgörs av.</p></td>
</tr>
<tr class="odd">
<td><p>Befintlig mall</p></td>
<td><p>Mallen baseras på en befintlig mallstrukturlista.</p></td>
</tr>
<tr class="even">
<td><p>Manuell</p></td>
<td><p>Om du vet exakt vilka reservdelar som vanligtvis måste bytas ut i serviceobjektet kanske du föredrar att skapa mallstrukturlistan manuellt. Du kan då se till att de komponenter som inkluderas i mallen avspeglar de faktiska kraven för din arbetsplats.</p></td>
</tr>
</tbody>
</table>


## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a>Använda mallstrukturlistan för ett serviceavtal eller en serviceorder

Mallstrukturlistan kan användas i ett serviceavtal och en serviceorder. Serviceavtalet omfattar vanligtvis en långtidsrelation med kunden. Ersättningshistoriken i servicestrukturlistan är användbar information att registrera i serviceavtalet.

Du kan också använda en strukturlistemall till en serviceorder om du vill registrera historiken över den service som har utförts på ett serviceobjekt.

## <a name="copy-the-history-of-a-service-bom"></a>Kopiera historiken för en servicestrukturlista

Du kan kopiera historiken för en servicestrukturlisterad från ett serviceavtal till ett annat serviceavtal. Genom att kopiera servicehistoriken mellan serviceavtalen kan du bibehålla ersättningsposterna för en artikel.

**Exempel**

Anta att du har ett treårigt serviceavtal för en kunds bil. Under denna period blir kunden van vid företagets bra service som företaget erbjuder kunden. Därför när avtalet förfaller vill kunden sätta upp ett nytt. Du kan nu förhandla fram ett mer fördelaktigt avtal för företaget. Eftersom du kan ha nytta av posten för ersättningskomponenter kopierar du servicestrukturlistans historik till det nya avtalet.

## <a name="modify-the-template-bom"></a>Ändra mallstrukturlistan

Om mallstrukturlistan inte har kopplats till något serviceobjekt kan du ändra eller ta bort rader. När mallstrukturlistan har kopplats till ett serviceobjekt kan du endast ändra den lokala versionen av strukturlistan. Om du vill kopiera inställningen för en lokal version av en mallstrukturlista kan du skapa en ny mallstrukturlista som baseras på den lokala versionen. Mer information finns i [Modifiera servicestrukturlista](modify-service-bom.md).

Om du ersätter en artikel i strukturlistan kan du registrera ersättningen på strukturlisteraden i strukturlistedesignern. Alternativt kan du skapa en serviceorderrad för ersättningsobjekten. Om en serviceorderrad skapas kan du fakturera ersättningsartikeln. Om du inte skapar någon serviceorderrad för en ersättning sparas registreringen av ersättningen för posterna så att du kan spåra serviceobjektets historik.

## <a name="change-how-information-on-the-bom-line-is-displayed"></a>Ändra visningen av information på strukturlisteraden

Du kan ändra sättet på vilket information på strukturlisteraderna visas i alla mallar och servicestrukturlistor. Ändringarna tillämpas på alla mallstrukturlistor och servicestrukturlistor. Inklusive de som är kopplade till ett serviceobjekt.

## <a name="set-up-number-sequences-for-template-boms"></a>Ställa in nummerserier för mallstrukturlistorna

Du måste ställa in två nummerserier om du vill använda mallstrukturlistor. Ställ in en nummerserie för mallstrukturlista och en för radnumret i strukturlistans historik.


> [!NOTE]
> <P>Nummerserier används i för att fördela identifierare till poster som krävs. Innan du kan tilldela en nummerserie till en mallstrukturlista eller en radnumret i strukturlistans historik, måste du ställa in nummerserier för streckkoder.</P>


## <a name="set-up-number-sequences"></a>Ställa in nummerserier

1.  På sidan **nummerserier**, skapat du nummerserier för mallstrukturlistor och radnumret för strukturlistans historik. 

2.  Klicka på **servicehantering** \> **inställningar** \> **servicehanteringsparametrar**.

3.  Klicka på **nummerserier**, och välj en nummerseriekod för den nummerseriereferenser som du skapat i formuläret **nummerserier**.

4.  Stäng formuläret så att ändringarna sparas.


> [!NOTE]
> <P>Radnumret i strukturlistans historik används av systemet för att koppla transaktionerna i strukturlistans historik till ett serviceavtal eller en serviceorder. Numret visas inte i användargränssnittet.</P>



## <a name="see-also"></a>Se även

[Skapa en strukturlistemall](create-template-bom.md)

[Hantera strukturlistemallar på objektrelationer](manage-template-boms-on-object-relations.md)

[Ändra en servicestrukturlista](modify-service-bom.md)

 


