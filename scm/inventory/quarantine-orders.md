---
title: "Karantänorder"
description: "Den här artikeln beskriver hur karantänorder används för att blockera lagret."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: ec3d54e8e08850cd81891e7058b2b787e08b0fb9
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Karantänorder
<a id="quarantine-orders" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver hur karantänorder används för att blockera lagret. 

Karantänorder kan användas för att blockera lagret. Du kanske vill sätta artiklar i karantän på grund av kvalitetskontroll. Lager som har varit i karantän överförs till ett karantänlagerställe. **Obs!** Om du använder avancerade lagerstyrningsprocesser (i Lagerstyrning) används bearbetning i karantänorder endast för returförsäljningsorder.

## Sätta lagerbehållningsartiklar i karantän
<a id="quarantine-onhand-inventory-items" class="xliff"></a>
När du sätter objekt i karantän kan du antingen skapa karantänorder manuellt eller ställa in systemet för att skapa karantänorder automatiskt under inkommande bearbetning. Skapa karantänorder automatiskt genom att välja alternativet **Karantänhantering** på fliken **Lagerpolicyer** på sidan **Artikelmodellgrupper**. Du måste även ange ett standardkarantänlagerställe i **Karantänlagerställe**-fältet för mottagande lagerställen. När det fysiska, tillgängliga lagret registreras i en inköpsorder eller produktionsorder, flyttas objekt i karantän automatisk till ett karantänlagerställe i Microsoft Dynamics 365 for Finance and Operations. Dessa förflyttningar inträffar eftersom karantänorderns status ändras till **Startat**. När du skapar karantänorder manuellt, artikeln måste inte vara inställd för karantänhantering i den associerade artikelmodellgruppen. För den här processen måste du ange lagerbehållning som ska finns i karantän och karantänlagerstället som ska användas. Du kan använda karantänorderstatusen för att planera processen.

## Karantänorder status
<a id="quarantine-order-statuses" class="xliff"></a>
Karantänorder kan ha följande status:

-   Skapad
-   Startat
-   Rapporterat som färdigt
-   Avslutat

### Skapad
<a id="created" class="xliff"></a>

När en karantänorder skapats manuellt, men posten är inte lagt i karantänlagerställe, karantänordern har status **Skapad**. Två lagertransaktioner skapas. En transaktion är en utlevererad transaktion som kan ha status **Har beställts**, **Fysiskt reserverat**, eller **Plockad**. Den andra transaktionen är en inleveranstransaktionen som kan ha statusen **Beställd** eller **Registrerad** vid karantänlagerstället. Du kan reservera, plocka och registrera uppdateringar i lagret med vanliga processer.

### Startat
<a id="started" class="xliff"></a>

När en karantänorder har statusen **Startat** lagret överförs från det vanliga lagret till karantänlagerstället och två lagertransaktioner skapas. En transaktion har status **dras av** och den andra transaktionen har status **Mottaget**. Samtidigt två lagertransaktioner skapas för att hantera transfer tur och retur. Dessa transaktioner är inte daterade. En transaktion har status **Reserverad fysiska**, och den andra transaktionen har status som **beställts**.

### Rapporterat som färdigt
<a id="reported-as-finished" class="xliff"></a>

Genom att klicka på **rapportera som färdiga**, du kan rapportera en började karantänorder som färdiga. Posten är frisläppt från karantänen men ännu inte flyttad tillbaka till den vanliga lager. Förflyttningen tillbaka till det vanliga lagret kan vara bearbetad via en alternativ artikelinförsel som kan initieras under processen Rapportera som färdig.

### Avslutat
<a id="ended" class="xliff"></a>

När en karantänorder avslutas, objektet flyttas från karantänlagerstället tillbaka till vanliga lagret. Status för objekt transaktion **säljs** på karantänlagerställe och **köpas** på regelbundna lager.

## Karantänorder skrot
<a id="quarantine-order-scrap" class="xliff"></a>
Som en del av karantänorderprocessen du kan kassera lagerartiklar. När du bearbetar kassationer, lagerstatusen kommer att sättas till **Sålt** genom en inleveranstransaktion från karantänlagerstället.

Se även
<a id="see-also" class="xliff"></a>
--------

[Lagerspärr](inventory-blocking.md)




