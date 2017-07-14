---
title: "Migrera från AX 2012 till Finance and Operations"
description: "Den här artikeln ger en översikt över migreringsalternativen för produkt- och lagerstyrning inom Dynamics 365 for Finance and Operations."
author: BibiSp
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 5ab19faddedae8cf61222762714609601b0ae96f
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017

---

# Migrera från AX 2012 till Finance and Operations
<a id="migrate-from-ax-2012-to-finance-and-operations" class="xliff"></a>

Det här avsnittet ger en översikt över migreringsalternativen för produkt- och lagerstyrning inom Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

Introduktion
<a id="introduction" class="xliff"></a>
------------

Under en uppgradering till Finance and Operations blockeras produkter om de är kopplade till en lagringsdimensionsgrupp som har inställningar som inte motsvarar kraven på inställningar för lagringsdimensionsgrupp i Finance and Operations. Efter uppgraderingen kan du däremot använda en uppsättning migreringsalternativ i processen **Ändra lagringsdimensionsgruppen för artiklar** för att tillåta produkter som har blockerats under uppgraderingen. Du kan sedan behandla transaktioner för dessa produkter. Vissa av dina artiklar kanske redan är kopplade till lagringsdimensionsgrupper där plats, lagerställe och platslagerdimensioner är aktiva och fysiskt spårade. I det här fallet kan du använda processen **Ändra lagringsdimensionsgruppen för artiklar** för att aktivera de artiklar som ska användas i lagerstyrningsprocesser. Denna funktion är användbar om du vill använda lagerstyrningsfunktionen för befintliga artiklar.

## Uppgradera till Finance and Operations när AX 2012 R3 WMSII används
<a id="upgrading-to-finance-and-operations-when-ax-2012-r3-wmsii-is-used" class="xliff"></a>
Finance and Operations stöder inte längre stöder äldre **WMSII**-moduler från Microsoft Dynamics AX 2012. I stället kan du använda den nya **lagerstyrningsmodulen**. Mer information finns i [Startsida för lagerstyrning](https://ax.help.dynamics.com/en/wiki/warehouse-management/). I tidigare versioner kunde lagerdimensionerna plats och lastpalls-ID väljas för ekonomiskt lager. Under uppgraderingsprocessen kan dock lagerdimensionen lastpalls-ID inte längre aktiveras för ekonomiskt lager. Alla produkter som hör till en lagringsdimensionsgrupp som använder lagerdimensionen lastpalls-ID blockeras och kommer inte att behandlas.

### Aktivera artiklar i Finance and Operations
<a id="enabling-items-in-finance-and-operations" class="xliff"></a>

I Finance and Operations måste artiklar som ska användas som en del av lagerstyrningsprocesser associeras med en lagringsdimensionsgrupp där parametern **Använd lagerstyrningsprocesser** väljs. När du väljer den här inställningen aktiveras lagerdimensionerna för plats, lagerställe, lagerstatus, plats och registreringsskylt. Du kan endast ändra denna typ av lagringsdimensionsgrupp för artiklar som redan är kopplade till lagringsdimensionsgrupper där platslagerdimensionen är aktiv.

### Artiklar som är spärrade för lageruppdateringar
<a id="items-that-are-blocked-for-inventory-updates" class="xliff"></a>

Så här visar du listan över frisläppta produkter som blockerades under uppgraderingen och inte kan behandlas. Klicka på **Lagerstyrning** &gt;**Inställningar** &gt; **Lager** &gt; **Objekt som har spärrats för lageruppdateringar**.

### Tillämpa blockerade produkter
<a id="reapplying-blocked-products" class="xliff"></a>

Om du vill upphäva blockeringen av produkter som blockerades under uppgraderingen måste du välja en ny lagringsdimensionsgruppen för produkterna. Observera att du kan ändra lagringsdimensionsgruppen även om det finns öppna lagertransaktioner. Om du vill använda artiklar som har blockerats under uppgraderingen har du två möjligheter:

-   Ändra lagringsdimensionsgruppen för artikeln till en lagringsdimensionsgrupp som endast använder plats, lagerställe och platslagerdimensioner. Ändringen innebär att lagerdimensionen lastpalls-ID inte längre används.
-   Ändra lagringsdimensionsgruppen för artikeln till en lagringsdimensionsgrupp som endast använder lagerstyrningsprocesser. Ändringen innebär att lagerdimensionen registreringsskylt används nu.

### Migreringsprocesser
<a id="migration-processes" class="xliff"></a>

I Finance and Operations är spårning en del av lagerstyrningsprocesserna. För de här processerna måste alla lagerställen och deras platser associeras med en platsprofil. Begreppsmässigt, om du vill använda lagerstyrningsprocesser, ska två processer hanteras:

-   Befintliga lagerställen måste aktiveras för lagerstyrningsprocesser.
-   Befintliga frisläppta produkter måste associeras med en ny lagringsdimensionsgrupp som använder lagerstyrningsprocesser.

Om källan lagringsdimensionsgrupper använder lagerdimension lastpalls-ID, måste placeringen av befintliga lager som används för lagerdimension lastpalls-ID associeras med en platsprofil där parametern **Använd registreringsskyltsspårning** väljs. Om befintliga lagerställen inte ska aktiveras för att använda lagerstyrningsprocesser kan du ändra lagringsdimensionsgrupper för den befintliga lagerbehållningen till grupper som endast hanterar endast plats, lagerställe och platslagerdimensioner.

### Använda lagerstyrningsprocesser
<a id="using-the-warehouse-management-processes" class="xliff"></a>

Innan du kan använda frisläppta produkter i **lagerstyrningsmodulen** måste produkterna använda en lagringsdimensionsgrupp där parametern **Använd lagerstyrningsprocesser** väljs.

#### Aktivera lagerställen för att använda lagerstyrningsprocesser
<a id="enable-warehouses-to-use-warehouse-management-processes" class="xliff"></a>

1.  Skapa minst en ny platsprofil.
2.  Klicka på **Lagerstyrning** &gt; **Inställningar** &gt; **Aktivera lagerstyrningsprocesser** &gt; **Aktivera inställning av lagerställe**.
3.  På sidan **Aktivera inställning av lagerstyrning** kan du lägga till de lagerställen som ska aktiveras. Du kan slutföra det här steget antingen direkt på sidan eller genom att använda Microsoft Office-integreringen.
4.  Tilldela en platsprofil till alla platser. Du kan enkelt slutföra det här steget genom att använda Microsoft Office-integreringen direkt från sidan. Du kan antingen exportera och importera data, eller använda dataenheten i [Datahantering](https://ax.help.dynamics.com/en/wiki/data-management-and-integration-through-data-entity/).
5.  Godkänn ändringarna. Som en del av valideringen kan olika valideringar av dataintegritet uppträda. Som en del av en större uppgraderingsprocess kan problem som uppstår justeras på källimplementeringen. I detta fall krävs ytterligare en datauppgradering.
6.  Behandla ändringarna.

#### Ändra lagringsdimensionsgruppen för artiklar, så att den använder lagerstyrningsprocesser
<a id="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes" class="xliff"></a>

1.  Skapa ett nytt värde för **Lagerstatus** och tilldela det som **Status-ID för lager som standard** i inställningarna för **Lagerstyrningsparametrar**.
2.  Skapa en ny lagringsdimensionsgrupp där parametern **Använd lagerstyrningsprocesser** väljs.
3.  På sidan **Reservationshierarki** kan du definiera en ny reservationshierarki enligt artikelns lagring och spårningsdimensionsgrupper.
4.  Skapa minst en eller flera sekvensgrupper som inkluderar minst samma enheter som används för artikelns lagerenheter.
5.  Klicka på **Lagerstyrning** &gt; **Inställningar** &gt; **Aktivera lagerstyrningsprocesser** &gt; **Ändra lagringsdimensionsgrupp för artiklar**.
6.  På sidan **Ändra lagringsdimensionsgruppen för artiklar** och lägg till artikelnummer, lagringsdimensionsgrupper och sekvensgrupper. Du kan slutföra det här steget direkt på sidan med hjälp av Microsoft Office-integrering eller genom att använda dataenhetsprocessen i [Datahantering](https://ax.help.dynamics.com/en/wiki/data-management-and-integration-through-data-entity/).
7.  Godkänn ändringarna. Som en del av valideringen kan olika valideringar av dataintegritet uppträda. Som en del av en större uppgraderingsprocess kan problem som uppstår justeras på källimplementeringen. I detta fall krävs ytterligare en datauppgradering.
8.  Behandla ändringarna. En uppdatering av alla lagerdimensioner kan ta en stund. Du kan övervaka förloppet med hjälp av batchjobbsuppgifterna.



