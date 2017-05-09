---
title: "Räkna om ersättningskostnader och försäkrade värden för anläggningstillgångsgrupper"
description: "Den här artikeln beskriver processen för att uppdatera ersättningskostnaden och de försäkrade värdena för anläggningstillgångar."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3261
ms.assetid: b8876f83-8772-4f2a-b277-12724e2a0c44
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 38f779274da370d436509e021cabf5b90ab08475
ms.lasthandoff: 03/31/2017


---

# <a name="recalculate-replacement-costs-and-insured-values-for-fixed-asset-groups"></a>Räkna om ersättningskostnader och försäkrade värden för anläggningstillgångsgrupper

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver processen för att uppdatera ersättningskostnaden och de försäkrade värdena för anläggningstillgångar.

Då och då kanske du får information om att kostnaden för att ersätta eller försäkra vissa anläggningstillgångar har ändrats. Din chef kanske till exempel informerar dig om att inflationen var 3 procent högre förra året, så att du måste öka ersättningskostnaden för alla anläggningstillgångar med 3 procent. 

Du kan redigera ersättningskostnaden och det försäkrade värdet för enskilda anläggningstillgångar i formuläret Anläggningstillgångar, men du kan använda formuläret Uppdatera ersättningskostnader och försäkrade värden om du vill uppdatera dessa värden för en grupp med anläggningstillgångar samtidigt. Den här informationen beskriver hur du uppdaterar värden för anläggningstillgångar eller för specifika tillgångar i grupperna.

## <a name="how-values-are-updated"></a> Hur värden uppdateras
Om du vill beräkna om ersättningskostnaden och det försäkrade värdet för anläggningstillgångsgruppen, måste du först ange den procent som den befintliga ersättningskostnaden och det försäkrade värdet ska ändras med, och sedan utföra den periodiska uppdateringen för att beräkna om värdena. Du anger procent i fälten Faktor för ersättningskostnad och Faktor för försäkrat värde i formuläret Anläggningstillgångsgrupper. Även om du anger dessa faktorer för hela gruppen med anläggningstillgångar, kan du när du använder formuläret Uppdatera ersättningskostnader och försäkrade värden välja att beräkna om ersättningskostnaden och det försäkrade värdet för enbart vissa anläggningstillgångar inom en grupp. 

När du använder formuläret Uppdatera ersättningskostnader och försäkrade värden för att beräkna om ersättningskostnaden och det försäkrade värdet för tillgången används följande formler:

-   \[(Tillgångsgruppens ersättningskostnadsfaktor / 100) + 1\] \* Tillgångens befintliga ersättningskostnad
-   \[(Tillgångsgruppens faktor för försäkrat värde / 100) + 1\] \* Tillgångens befintliga försäkrade värde

> [!NOTE] 
> När du använder Uppdatera ersättningskostnader och försäkrade värde uppdateras både ersättningskostnaden och det försäkrade värdet för valda tillgångar, men du kan inte ange att bara ett värde ska uppdateras. Om du vill att det ena ska behålla sitt värde och bara uppdatera det andra, anger du 0 (noll) som faktor i formuläret Anläggningstillgångsgrupper. En faktor som är noll eller tom gör att beräkningen hoppas över i uppdateringen. Det bokförda värdet och det bokförda nettovärdet för anläggningstillgångar påverkas inte av den periodiska uppdateringen. 

## <a name="how-to-use-a-date-to-select-which-items-to-update"></a> Välj vilka artiklar som ska uppdateras med hjälp av ett datum
Som standard uppdaterar uppdateringsprocessen de valda tillgångar som inte har uppdaterats vid aktuellt datum, men som kan ha uppdaterats tidigare. Till exempel, &lt; aktuellt datum innebär "före idag". Du kan ändra datumet i formuläret Uppdatera ersättningskostnader och försäkrade värden genom att klicka på knappen Välj. Datumvillkoret som du anger jämförs med datumet för den senaste periodiska uppdateringen för tillgången (fältet Senaste periodiska värde/kostnadsuppdatering i formuläret Anläggningstillgångar). Varje gång som du uppdaterar ersättningskostnaden eller det försäkrade värdet för en anläggningstillgång, uppdateras fältet Senaste periodiska värde/kostnadsuppdatering automatiskt med aktuellt datum. 

Exempel 

Du uppdaterade ersättningskostnaden för grupperna Fordon, Kontorsmöbler och Byggnader med 5 procent i går, och du anser nu att dessa tillgångar är tillräckligt uppdaterade. Om du vill utesluta dessa tillgångar när du uppdaterar alla andra tillgångar i dag, anger du ett datum i fältet som infaller före i går (&lt; gårdagens datum), eftersom den senaste periodiska uppdateringen av fordon, kontorsmöbler och byggnadsgrupper gjordes utanför det datumintervall som du anger.

## <a name="cumulative-effect-of-each-update"></a> Ackumulerad effekt av varje uppdatering
Varje uppdatering har ackumulerad effekt. Därför bör du planera dina uppdateringar noggrant. Om du till exempel ökar alla tillgångar med 3 procent på torsdag och sedan ökar kontorsmöbler med 4 procent på fredag, kommer kontorsmöbler att öka med sammanlagt 7,12 procent.

## <a name="scenario"></a>Scenario
Din chef meddelar dig om följande ändringar av anläggningstillgångarna:
-   Öka ersättningskostnaden för alla anläggningstillgångar, utom datorer, med 3,25 procent.
-   Öka ersättningskostnaden för alla kontorsmöbler med ytterligare 1 procent.
-   Minska ersättningskostnaden och det försäkrade värdet på alla datorer med 10 procent.

Du gör följande ändringar:
1.  I formuläret Anläggningstillgångsgrupper skriver du för alla anläggningstillgångsgrupper förutom gruppen kontorsmöbler och datorer skriver du 3,25 i fältet Faktor för ersättningskostnad 0 i fältet Faktor för försäkrat värde.
2.  För gruppen Kontorsmöbler skriver du 4,25 i fältet Faktor för ersättningskostnad och0 i Faktor för försäkrat värde..
3.  För gruppen Datorer skriver du -10 i fältet Faktor för ersättningskostnad och-10 i Faktor för försäkrat värde..
4.  I formuläret Uppdatera ersättningskostnaderna och det försäkrade värdet, klickar du på OK för att omberäkna alla anläggningstillgångar.

Nästa dag informerar chefen om att datorerna har minskat 8 procent i stället för 10 procent, så du måste korrigera ersättningskostnaden och det försäkrade värdet. Du rättar till felet med någon av följande två metoder:
-   Ändra manuellt fälten Försäkrat värde och Ersättningskostnad i formuläret Anläggningstillgång för varje anläggningstillgång i gruppen Datorer. Beräkna och registrera värdena manuellt om du har minskat det ursprungliga beloppet med 8 procent. Genom att använda den här metoden, använder du inte formuläret Uppdatera ersättningskostnaderna och försäkrade värden.
-   Ange faktorer för ersättningskostnad och försäkrat värde för gruppen Datorer fälten Ange faktorer för ersättningskostnad och försäkrat värdet i formuläret Anläggningstillgångsgrupper. Då återställs tillgångarna till sitt ursprungliga värde (före minskningen på 10 procent) och en 8 procents minskning används på det ursprungliga värdet. Använd sedan Uppdatera ersättningskostnader och försäkrade värden för att beräkna om värdena, beroende på de faktorer som du anger.

> [!NOTE]  
> Du kan inte ångra faktorn -10 genom att registrera det positiva talet 10 (eller faktorn 2, skillnaden mellan -10 och -8), eftersom beloppen inte beräknas som du har tänkt dig. 






