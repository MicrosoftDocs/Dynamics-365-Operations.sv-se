---
title: Reparationshantering
description: "Gruppera problem systematiskt så att det blir enklare att föreslå lösningar som tidigare har lyckats."
author: YuyuScheller
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 937571968c6956ce3dba1427082b298983540f59
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="repair-management"></a>Reparationshantering       

[!include [banner](../includes/banner.md)]


Inför reparationshantering kan du gruppera problem systematiskt. Detta gör det enklare att föreslå lösningar som tidigare har lyckats.

Du kan ställa in symptom, diagnos och upplösning. Dessa kan senare användas när du får ett liknande objekt för reparation. Du kan också ställa in reparationsfaser så att du kan följa ärendeförloppet.

## <a name="setting-up-repair-management"></a>Ställa in reparationshantering.

Använd följande inställningsformulär när du anger information som används för att ange symptomen, diagnosen och lösningen för reparationen.

1.  Klicka på **servicehantering**\>**inställningar**\>**reparation**\>**villkor**.

2.  Klicka på **servicehantering**\>**inställningar**\>**reparation**\>**symptomområden**.

3.  Klicka på **servicehantering**\>**inställningar**\>**reparation**\>**diagnosområden**.

4.  Klicka på **servicehantering**\>**inställningar**\>**reparation**\>**lösningar**.

5.  Klicka på **servicehantering**\>**inställningar**\>**reparation**\>**reparationssteg**.

## <a name="symptoms-and-conditions"></a>Symptom och villkor

Symptom är hur kunden karaktäriserar problemet. Symptom omfattar kundens observationer som anger reparationsbehovet.

Du kan ställa in symptomområden, symptomkoder och tillstånd. Symptomområden omfattar felområden och symptomkoden täcker in felsymptomet. Villkoret beskriver situationen eller miljö som finns när problemet uppstår.

**Exempel**

En dator tas in för reparation eftersom hårddisken misslyckas efter användning lång tid. Hårddiskfel medför ett blåskärmsfel. Den tekniker som tar emot datorn övergår i följande symptom och villkor:

1.  Symptomområden är hårddisken

2.  Symptomkoden är fel med blå skärm

3.  Villkoret är att hårddisken havererar efter utökad användning

## <a name="diagnosis-and-resolutions"></a>Diagnoser och lösningar

Diagnos- och lösningsfälten innehåller information ur reparationsperspektiv. Dessa är de steg som en tekniker har gått igenom för att undersöka problemet.

Diagnosområden omfattar den åtgärd som måste vidtas för att lösa problemet. Diagnoskoden är hur problemet har hanterats, och lösningen kan vara att artikeln har reparerats, bytts ut eller att ordern annullerades av kunden. Om till exempel datorn har reparerats kan diagnosområdet vara "defekt del", diagnoskoden vara "nytt grafikkort installerat" och lösningen "utbytt".

## <a name="repair-stages"></a>Reparationsfaser

Reparationsfaserna anger reparationsförloppet. Reparationsfasen har avslutsparametern **Avslutad** som anger att reparationen är färdig och att färdigdatum och -tid har registrerats.

## <a name="applying-repair-management"></a>Tillämpa reparationshantering

Om du vill tillämpa reparationshantering på en artikel måste artikeln ställas in med en serviceobjektrelation på en serviceorder. Från serviceordern kan du skapa en reparationsrad med information om det aktuella ärendet. På reparationsraden anger du serviceobjektet som repareras och information om symptom, diagnos och utförande. Du kan också skapa en anteckning för reparationsraden.

Du kan skapa reparationsrader för varje steg i reparationsprocessen.

## <a name="create-a-repair-line-on-a-service-order"></a>Skapa en reparationsrad på en serviceorder

1.  Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.

2.  Markera serviceordern med serviceobjektet som behöver repareras.

3.  Klicka på **reparation**\>**reparationsrader** för att öppna formuläret **reparationsrader**.

4.  Skapa en ny rad genom att trycka på CTRL+N.

5.  Markera ett serviceobjekt. Du kan välja valfritt serviceobjekt som har ställts in med en objektrelation på serviceordern.

6.  Markera någon av de förinställda symptomen, diagnoserna och utförandevärdena som är relevanta på reparationsraden och, om det behövs, klicka på fliken **anteckning** om du vill skapa en anteckning på reparationsraden.

7.  Spara den nya reparationsraden genom att trycka på CTRL+S. Fältet **skapat datum och klockslag** på fliken **allmänt** i formuläret **reparationsrader** uppdateras med tidpunkten då raden sparas.

## <a name="tracking-progress-and-resolving-a-repair-issue"></a>Uppföljning och lösa ett problem med reparation

Du kan ställa in reparationsfaser för en reparationsrad om du vill spåra ärendeförloppet.

När en reparera problemet är löst kan stänga du reparationsraden. Ange reparationsfasen till en fas där egenskapen **avslutad** är aktiverad. Aktuellt datum och aktuell tid registreras som sluttid på raden.

## <a name="close-a-repair-line-for-a-resolved-issue"></a>Stänga en reparationsfas för ett löst ärende

1.  Öppna formuläret **Reparationsrader**. Följ proceduren tidigare i det här avsnittet och skapa en reparationsrad.

2.  Markera reparationsraden med reparationsärendet som du vill stänga.

3.  I fältet **Reparationssteg** välj ett steg med egenskapen **Avslutad** aktiverad.

  



