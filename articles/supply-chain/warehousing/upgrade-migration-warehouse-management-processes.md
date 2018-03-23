---
title: "Migrera produkter och lagerhantering från AX 2012 till Finance and Operations"
description: "I det här avsnittet finns en översikt över produkt- och lagerhantering samt migreringsalternativ."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 4d94a5b2cc0e9ea144fbefc97cc27a2920016358
ms.contentlocale: sv-se
ms.lasthandoff: 03/08/2018

---

# <a name="migrate-products-and-warehouse-management-from-ax-2012-to-finance-and-operations"></a>Migrera produkter och lagerhantering från AX 2012 till Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet ger en översikt över migreringsalternativen för produkt- och lagerstyrning inom Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

<a name="introduction"></a>Introduktion
------------

Under en uppgradering till Finance and Operations blockeras produkter om de är kopplade till en lagringsdimensionsgrupp som har inställningar som inte motsvarar kraven på inställningar för lagringsdimensionsgrupp i Finance and Operations. Efter uppgraderingen kan du däremot använda en uppsättning migreringsalternativ i processen **Ändra lagringsdimensionsgruppen för artiklar** för att tillåta produkter som har blockerats under uppgraderingen. Du kan sedan behandla transaktioner för dessa produkter. Vissa av dina artiklar kanske redan är kopplade till lagringsdimensionsgrupper där plats, lagerställe och platslagerdimensioner är aktiva och fysiskt spårade. I det här fallet kan du använda processen **Ändra lagringsdimensionsgruppen för artiklar** för att aktivera de artiklar som ska användas i lagerstyrningsprocesser. Denna funktion är användbar om du vill använda lagerstyrningsfunktionen för befintliga artiklar.

## <a name="upgrading-to-finance-and-operations-when-ax-2012-r3-wmsii-is-used"></a>Uppgradera till Finance and Operations när AX 2012 R3 WMSII används
Finance and Operations stöder inte längre stöder äldre **WMSII**-moduler från Microsoft Dynamics AX 2012. I stället kan du använda den nya **lagerstyrningsmodulen**. I tidigare versioner kunde lagerdimensionerna plats och lastpalls-ID väljas för ekonomiskt lager. Under uppgraderingsprocessen kan dock lagerdimensionen lastpalls-ID inte längre aktiveras för ekonomiskt lager. Alla produkter som hör till en lagringsdimensionsgrupp som använder lagerdimensionen lastpalls-ID blockeras och kommer inte att behandlas.

### <a name="enabling-items-in-finance-and-operations"></a>Aktivera artiklar i Finance and Operations

I Finance and Operations måste artiklar som ska användas som en del av lagerstyrningsprocesser associeras med en lagringsdimensionsgrupp där parametern **Använd lagerstyrningsprocesser** väljs. När du väljer den här inställningen aktiveras lagerdimensionerna för plats, lagerställe, lagerstatus, plats och registreringsskylt. Du kan endast ändra denna typ av lagringsdimensionsgrupp för artiklar som redan är kopplade till lagringsdimensionsgrupper där platslagerdimensionen är aktiv.

### <a name="items-that-are-blocked-for-inventory-updates"></a>Artiklar som är spärrade för lageruppdateringar

Så här visar du listan över frisläppta produkter som blockerades under uppgraderingen och inte kan behandlas. Klicka på **Lagerstyrning** &gt;**Inställningar** &gt; **Lager** &gt; **Objekt som har spärrats för lageruppdateringar**.

### <a name="reapplying-blocked-products"></a>Tillämpa blockerade produkter

Om du vill upphäva blockeringen av produkter som blockerades under uppgraderingen måste du välja en ny lagringsdimensionsgruppen för produkterna. Observera att du kan ändra lagringsdimensionsgruppen även om det finns öppna lagertransaktioner. Om du vill använda artiklar som har blockerats under uppgraderingen har du två möjligheter:

-   Ändra lagringsdimensionsgruppen för artikeln till en lagringsdimensionsgrupp som endast använder plats, lagerställe och platslagerdimensioner. Ändringen innebär att lagerdimensionen lastpalls-ID inte längre används.
-   Ändra lagringsdimensionsgruppen för artikeln till en lagringsdimensionsgrupp som endast använder lagerstyrningsprocesser. Ändringen innebär att lagerdimensionen registreringsskylt används nu.

### <a name="migration-processes"></a>Migreringsprocesser

I Finance and Operations är spårning en del av lagerstyrningsprocesserna. För de här processerna måste alla lagerställen och deras platser associeras med en platsprofil. Begreppsmässigt, om du vill använda lagerstyrningsprocesser, ska två processer hanteras:

-   Befintliga lagerställen måste aktiveras för lagerstyrningsprocesser.
-   Befintliga frisläppta produkter måste associeras med en ny lagringsdimensionsgrupp som använder lagerstyrningsprocesser.

Om källan lagringsdimensionsgrupper använder lagerdimension lastpalls-ID, måste placeringen av befintliga lager som används för lagerdimension lastpalls-ID associeras med en platsprofil där parametern **Använd registreringsskyltsspårning** väljs. Om befintliga lagerställen inte ska aktiveras för att använda lagerstyrningsprocesser kan du ändra lagringsdimensionsgrupper för den befintliga lagerbehållningen till grupper som endast hanterar endast plats, lagerställe och platslagerdimensioner.

### <a name="using-the-warehouse-management-processes"></a>Använda lagerstyrningsprocesser

Innan du kan använda frisläppta produkter i **lagerstyrningsmodulen** måste produkterna använda en lagringsdimensionsgrupp där parametern **Använd lagerstyrningsprocesser** väljs.

#### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Aktivera lagerställen för att använda lagerstyrningsprocesser

1.  Skapa minst en ny platsprofil.
2.  Klicka på **Lagerstyrning** &gt; **Inställningar** &gt; **Aktivera lagerstyrningsprocesser** &gt; **Aktivera inställning av lagerställe**.
3.  På sidan **Aktivera inställning av lagerstyrning** kan du lägga till de lagerställen som ska aktiveras. Du kan slutföra det här steget antingen direkt på sidan eller genom att använda Microsoft Office-integreringen.
4.  Tilldela en platsprofil till alla platser. Du kan enkelt slutföra det här steget genom att använda Microsoft Office-integreringen direkt från sidan. Du kan antingen exportera och importera data, eller använda dataenheten i [Datahantering](../../dev-itpro/data-entities/data-entities.md).
5.  Godkänn ändringarna. Som en del av valideringen kan olika valideringar av dataintegritet uppträda. Som en del av en större uppgraderingsprocess kan problem som uppstår justeras på källimplementeringen. I detta fall krävs ytterligare en datauppgradering.
6.  Behandla ändringarna.

#### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Ändra lagringsdimensionsgruppen för artiklar, så att den använder lagerstyrningsprocesser

1.  Skapa ett nytt värde för **Lagerstatus** och tilldela det som **Status-ID för lager som standard** i inställningarna för **Lagerstyrningsparametrar**.
2.  Skapa en ny lagringsdimensionsgrupp där parametern **Använd lagerstyrningsprocesser** väljs.
3.  På sidan **Reservationshierarki** kan du definiera en ny reservationshierarki enligt artikelns lagring och spårningsdimensionsgrupper.
4.  Skapa minst en eller flera sekvensgrupper som inkluderar minst samma enheter som används för artikelns lagerenheter.
5.  Klicka på **Lagerstyrning** &gt; **Inställningar** &gt; **Aktivera lagerstyrningsprocesser** &gt; **Ändra lagringsdimensionsgrupp för artiklar**.
6.  På sidan **Ändra lagringsdimensionsgruppen för artiklar** och lägg till artikelnummer, lagringsdimensionsgrupper och sekvensgrupper. Du kan slutföra det här steget direkt på sidan med hjälp av Microsoft Office-integrering eller genom att använda dataenhetsprocessen i [Datahantering](../../dev-itpro/data-entities/data-entities.md).
7.  Godkänn ändringarna. Som en del av valideringen kan olika valideringar av dataintegritet uppträda. Som en del av en större uppgraderingsprocess kan problem som uppstår justeras på källimplementeringen. I detta fall krävs ytterligare en datauppgradering.
8.  Behandla ändringarna. En uppdatering av alla lagerdimensioner kan ta en stund. Du kan övervaka förloppet med hjälp av batchjobbsuppgifterna.



