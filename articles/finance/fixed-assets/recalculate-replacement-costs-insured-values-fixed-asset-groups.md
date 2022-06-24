---
title: Räkna om ersättningskostnader och försäkrade värden för Anläggningstillgångsgrupper
description: Den här artikeln beskriver processen för att uppdatera ersättningskostnaden och de försäkrade värdena för anläggningstillgångar.
author: moaamer
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 3261
ms.assetid: b8876f83-8772-4f2a-b277-12724e2a0c44
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b461438ca3fef36e69100379e84f4c0d402e53e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853479"
---
# <a name="recalculate-replacement-costs-and-insured-values-for-fixed-asset-groups"></a>Räkna om ersättningskostnader och försäkrade värden för Anläggningstillgångsgrupper

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver processen för att uppdatera ersättningskostnaden och de försäkrade värdena för anläggningstillgångar.

Då och då kanske du får information om att kostnaden för att ersätta eller försäkra vissa anläggningstillgångar har ändrats. Din chef kanske till exempel informerar dig om att inflationen var 3 procent högre förra året, så att du måste öka ersättningskostnaden för alla anläggningstillgångar med 3 procent. 

Du kan redigera ersättningskostnaden och det försäkrade värdet för enskilda anläggningstillgångar på sidan **Anläggningstillgångar**, men du kan använda sidan **Uppdatera ersättningskostnader och försäkrade värden** om du vill uppdatera dessa värden för en grupp med anläggningstillgångar samtidigt. Den här informationen beskriver hur du uppdaterar värden för anläggningstillgångar eller för specifika tillgångar i grupperna.

## <a name="how-values-are-updated"></a> Hur värden uppdateras
Om du vill beräkna om ersättningskostnaden och det försäkrade värdet för Anläggningstillgångsgruppen, måste du först ange den procent som den befintliga ersättningskostnaden och det försäkrade värdet ska ändras med, och sedan utföra den periodiska uppdateringen för att beräkna om värdena. Du anger procent i fälten **Faktor för ersättningskostnad** och **Faktor för försäkrat värde** på sidan **Anläggningstillgångsgrupper**. Även om du anger dessa faktorer för hela gruppen med anläggningstillgångar, kan du när du använder sidan **Uppdatera ersättningskostnader och försäkrade värden** välja att beräkna om ersättningskostnaden och det försäkrade värdet för enbart vissa anläggningstillgångar inom en grupp. 

När du använder sidan **Uppdatera ersättningskostnader och försäkrade värden** för att beräkna om ersättningskostnaden och det försäkrade värdet för tillgången används följande formler:

-   \[(Tillgångsgruppens ersättningskostnadsfaktor / 100) + 1\] \* Tillgångens befintliga ersättningskostnad
-   \[(Tillgångsgruppens faktor för försäkrat värde / 100) + 1\] \* Tillgångens befintliga försäkrade värde

> [!NOTE] 
> När du använder sidan **Uppdatera ersättningskostnader och försäkrade värden** uppdateras både ersättningskostnaden och det försäkrade värdet för valda tillgångar, men du kan inte ange att bara ett värde ska uppdateras. Om du vill att det ena ska behålla sitt värde och bara uppdatera det andra, anger du 0 (noll) som faktor på sidan **Anläggningstillgångsgrupper**. En faktor som är noll eller tom gör att beräkningen hoppas över i uppdateringen. Det bokförda värdet och det bokförda nettovärdet för anläggningstillgångar påverkas inte av den periodiska uppdateringen. 

## <a name="how-to-use-a-date-to-select-which-items-to-update"></a> Välj vilka artiklar som ska uppdateras med hjälp av ett datum
Som standard uppdaterar uppdateringsprocessen de valda tillgångar som inte har uppdaterats vid aktuellt datum, men som kan ha uppdaterats tidigare. Till exempel, &lt; aktuellt datum innebär "före idag". Du kan ändra datumet på sidan **Uppdatera ersättningskostnader och försäkrade värden** genom att klicka på knappen **Välj**. Datumvillkoret som du anger jämförs med datumet för den senaste periodiska uppdateringen för tillgången (fältet **Senaste periodiska värde/kostnadsuppdatering** på sidan **Anläggningstillgångar**). Varje gång som du uppdaterar ersättningskostnaden eller det försäkrade värdet för en anläggningstillgång, uppdateras fältet **Senaste periodiska värde/kostnadsuppdatering** automatiskt med aktuellt datum. 

Exempel 

Du uppdaterade ersättningskostnaden för grupperna Fordon, Kontorsmöbler och Byggnader med 5 procent i går, och du anser nu att dessa tillgångar är tillräckligt uppdaterade. Om du vill utesluta dessa tillgångar när du uppdaterar alla andra tillgångar i dag, anger du ett datum i fältet **Senaste periodiska värde/kostnadsuppdatering** som infaller före i går (&lt;gårdagens datum), eftersom den senaste periodiska uppdateringen av **fordon**, **kontorsmöbler** och **byggnadsgrupper** gjordes utanför det datumintervall som du anger.

## <a name="cumulative-effect-of-each-update"></a> Ackumulerad effekt av varje uppdatering
Varje uppdatering har ackumulerad effekt. Därför bör du planera dina uppdateringar noggrant. Om du till exempel ökar alla tillgångar med 3 procent på torsdag och sedan ökar kontorsmöbler med 4 procent på fredag, kommer kontorsmöbler att öka med sammanlagt 7,12 procent.

## <a name="scenario"></a>Scenario
Din chef meddelar dig om följande ändringar av anläggningstillgångarna:
-   Öka ersättningskostnaden för alla anläggningstillgångar, utom datorer, med 3,25 procent.
-   Öka ersättningskostnaden för alla kontorsmöbler med ytterligare 1 procent.
-   Minska ersättningskostnaden och det försäkrade värdet på alla datorer med 10 procent.

Du gör följande ändringar:
1.  På sidan **Anläggningstillgångsgrupper** för alla anläggningstillgångsgrupper förutom gruppen **kontorsmöbler** och **datorer** skriver du 3,25 i fältet **Faktor för ersättningskostnad** och 0 i fältet **Faktor för försäkrat värde**.
2.  För gruppen **Kontorsmöbler** skriver du 4,25 i fältet **Faktor för ersättningskostnad** och 0 i fältet **Faktor för försäkrat värde**.
3.  För gruppen **Datorer** skriver du -10 i fältet **Faktor för ersättningskostnad** och -10 i fältet **Faktor för försäkrat värde**.
4.  På sidan **Uppdatera ersättningskostnaderna och det försäkrade värdet**, klickar du på **OK** för att omberäkna alla anläggningstillgångar.

Nästa dag informerar chefen om att datorerna har minskat 8 procent i stället för 10 procent, så du måste korrigera ersättningskostnaden och det försäkrade värdet. Du rättar till felet med någon av följande två metoder:
-   Ändra manuellt i fälten **Försäkrat värde** och **Ersättningskostnad** på sidan **Anläggningstillgångar** för varje anläggningstillgång i gruppen **Datorer**. Beräkna och registrera värdena manuellt om du har minskat det ursprungliga beloppet med 8 procent. Genom att använda den här metoden behöver du inte använda sidan **Uppdatera ersättningskostnaderna och försäkrade värden**.
-   Ange faktorer för ersättningskostnad och försäkrat värde för gruppen **Datorer** i fälten **Faktor för ersättningskostnad** och **Faktor för försäkrat värde** på sidan **Anläggningstillgångsgrupper**. Då återställs tillgångarna till sitt ursprungliga värde (före minskningen på 10 procent) och en 8 procents minskning används på det ursprungliga värdet. Använd sedan sidan **Uppdatera ersättningskostnader och försäkrade värden** för att beräkna om värdena, beroende på de faktorer som du anger.

> [!NOTE]  
> Du kan inte ångra faktorn -10 genom att registrera det positiva talet 10 (eller faktorn 2, skillnaden mellan -10 och -8), eftersom beloppen inte beräknas som du har tänkt dig. 







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
