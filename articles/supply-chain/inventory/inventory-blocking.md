---
title: Lagerspärr
description: Det här avsnittet ger en översikt över lagerspärren, som är en del av kvalitetsinspektionsprocessen i Supply Chain Management. Du kan använda lagerspärr för att förhindra att artiklar bearbetas eller förbrukas.
author: perlynne
manager: tfehr
ms.date: 01/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8807756f16a08f9818f998ce19a8088c7dd37405
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437738"
---
# <a name="inventory-blocking"></a>Lagerspärr

[!include [banner](../includes/banner.md)]

Det här avsnittet ger en översikt över lagerspärren, som är en del av kvalitetsinspektionsprocessen i Supply Chain Management. Du kan använda lagerspärr för att förhindra att artiklar bearbetas eller förbrukas.

Du kan spärra lagerartiklar på fäljande sätt:
-   Manuellt
-   Genom att skapa en kvalitetsorder
-   Genom att använda en process som genererar en kvalitetsorder
-   Genom att använda lagerstatusspärr

## <a name="blocking-items-manually"></a>Spärra artiklar manuellt
Du kan spärra en kvantitet för en artikel, genom att skapa en transaktion på sidan **Lagerspärr**. Endast artiklar som finns i lager kan spärras manuellt. För manuellt spärrade kvantiteter måste du bestämma om plancerade aktiviteter inkluderar förväntade inleveranser som förväntad lagerbehållning. Förväntad inleveranser är spärrade artiklar som förväntas vara tillgängliga som lagerbehållning efter inspektion. Du kan behålla de förväntade datumet. Som standard väljs alternativet **Förväntade inleveranser** för artiklar som är spärrade via en kvalitetsorder. Du kan avbryta en manuell blockering för en kvantitet, genom att radera transaktionen på sidan **Lagerspärr**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Spärra artiklar genom att skapa en kvalitetsorder
Du kan ange artiklar som måste kontrolleras, genom att skapa en kvalitetsorder på sidan **Kvalitetsorder**. När du skapar en kvalitetsorder, spärras kvantiteten för en artikel som du anger. Samplingsplanen som är kopplad till n kvalitetsorder kontrollerar bara kvantiteten av artiklarna som måste kontrolleras, inte kvantiteten som har spärrats. Oavsett vilken kvantitet som skickas på inspektion, är den kvantitet som spärras den kvantitet av artikeln som anges på kvalitetsordern.

> [!NOTE]
> Att använda både batchens utgångsdatum och spärr av lagerstatusfunktioner stöds inte av huvudplaneringen. Detta kan resultera i dubbel uteslutning av lagerbehållning, som kan inträffa under huvudplaneringen. Vi rekommenderar att du använder koder för batchdispositionskod, i stället för lagerstatus, för spärr av utgångna batchar.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Spärra artiklar med en process som genererar en kvalitetsorder
Om en kvalitetsprocess anger att en artikel måste inspekteras kommer en kvantitet av artikeln att spärras automatiskt. Så när en kvalitetsorder genereras automatiskt kontrollerar den artikelsamplingsprovsplan som hör till kvalitetsordern både kvantiteten av artiklar som är spärrade och kvantiteten som ska kontrolleras. Om alternativet **Fullständig spärr** på sidan **Artikelsampling** har markerats är den fullständiga kvantiteten på till exempel en inköpsorderrad spärrad under inspektion oavsett artikelsamplingskvantiteten.
### <a name="example"></a>Exempel

I följande exempel skapas en kvalitetsorder när en följesedel för inköpsorder bokförs. På sidan **Kvalitetsassociationer** anger du att bokföring av en följesedel för inköpsorder som den process som aktiverar kvalitetsordern.

|Inställningar                                                                     |Användaråtgärd                 |Resultat             |
|--------------------------------------------------------------------------|----------------------------|-------------------|
| En kvalitetsassociation anger att en kvalitetsorder måste genereras vid bokföringen av en följesedel för inköpsorder. Artikelsamplingsinställningar för kvalitetsordern anger att 10 % av inköpsorderradkvantiteten måste kontrolleras. Eftersom alternativet **Fullständig spärr** är markerad i artikelsamplingsinställningarna måste hela kvantiteten för inköpsorderraden vara spärrad vid inspektion oavsett kvantiteten som skickas för inspektion. | Följesedeln bokförs. | En kvalitetsorder genereras. 10 % av inköpsorderkvantiteten för artikeln skickas för inspektion. Den fullständiga kvantiteten på inköpsorderraden är spärrad. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Spärra artiklar med lagerstatusspärr
Du kan ange vilka sorters lagerstatus som är spärrar genom att använda parametern **Lagerspärr** på sidan **Lagerstatus**.  Du kan inte använda lagerstatus som spärrstatus för tillverkningsorder, försäljningsorder, överföringsorder, utgående transaktioner eller projektintegrationer. För utgående arbete, använd artiklar med tillgänglig lagerstatus. Om det finns artiklar med statusen **bruten** och huvudplaneringen körs på dessa artiklar, betraktas artiklarna saknade, och lagret fylls automatiskt på.



<a name="additional-resources"></a>Ytterligare resurser
--------

[Skapa och underhålla en lagerblockering](tasks/create-maintain-inventory-blocking.md)

[Kvalitetshanteringsprocesser](quality-management-processes.md)

[Kontrollera kvaliteten på varor](tasks/inspect-quality-goods.md)
