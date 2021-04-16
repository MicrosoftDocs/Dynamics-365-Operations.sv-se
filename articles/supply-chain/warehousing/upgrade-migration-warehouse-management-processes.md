---
title: Uppgradera lagerstyrning från Microsoft DynamicsAX 2012 till Supply Chain Management
description: I det här avsnittet finns en översikt över produkt- och lagerhantering samt migreringsalternativ.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fe8969345b8499bacfeecb0a1535174ce988eabc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837427"
---
# <a name="upgrade-warehouse-management-from-microsoft-dynamics-ax-2012-to-supply-chain-management"></a>Uppgradera lagerstyrning från Microsoft DynamicsAX 2012 till Supply Chain Management 


[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en översikt över hur du uppgraderar från Microsoft Dynamics AX 2012 R3, med modulen WMSII till Supply Chain Management.

Supply Chain Management stöder inte längre stöder äldre **WMSII**-modulen från Microsoft Dynamics AX 2012. I stället kan du använda den nya **lagerstyrningsmodulen**. I WMSII-modulen kan lagerdimensionerna för lagerställe och lastpalls-ID väljas för ekonomiskt lager, med lagerdimension för lastpalls-ID kan inte användas för ekonomiskt lager i Supply Chain Management.

Under en uppgradering har alla produkter som hör till en lagringsdimensionsgrupp som använder lagerdimensionen för lastpalls-ID identifierats, har markerats som spärrade och har inte bearbetats för uppgradering.

## <a name="upgrading-to-supply-chain-management-when-ax-2012-r3-wmsii-is-used"></a>Uppgradera till Supply Chain Management när AX 2012 R3 WMSII används
Efter uppgraderingen kan du däremot använda en uppsättning alternativ i formuläret **Ändra lagringsdimensionsgruppen för artiklar** för att avblockera produkter som har blockerats under uppgraderingen och sedan bearbeta transaktioner för dessa produkter.

### <a name="enabling-items-in-supply-chain-management"></a>Aktivera artiklar i Supply Chain Management 
Den här ändringen krävs eftersom i Supply Chain Management är spårning en del av lagerstyrningsprocesserna. För de här processerna måste alla lagerställen och deras platser associeras med en platsprofil. Om du vill använda lagerstyrningsprocesser, ska följande konfigureras:
-   Befintliga lagerställen måste aktiveras för lagerstyrningsprocesser. 
-   Befintliga frisläppta produkter måste associeras med en lagringsdimensionsgrupp som använder lagerstyrningsprocesser. 

Om källan lagringsdimensionsgrupper använder lagerdimension lastpalls-ID, måste placeringen av befintliga lager som används för lagerdimension lastpalls-ID associeras med en platsprofil där parametern **Använd registreringsskyltsspårning** väljs. Om befintliga lagerställen inte ska aktiveras för att använda lagerstyrningsprocesser kan du ändra lagringsdimensionsgrupper för den befintliga lagerbehållningen till grupper som endast hanterar endast plats, lagerställe och platslagerdimensioner. 

> [!NOTE] 
>  Du kan ändra lagringsdimensionsgruppen för artiklar även om det finns öppna lagertransaktioner.

## <a name="find-products-that-were-blocked-because-of-pallet-id"></a>Sök efter produkter som har blockerats på grund av lastpalls-ID
Så här visar du listan över frisläppta produkter som blockerades under uppgraderingen och inte kan behandlas. Klicka på **Lagerstyrning** &gt;**Inställningar** &gt; **Lager** &gt; **Objekt som har spärrats för lageruppdateringar**.

## <a name="change-storage-dimension-group-for-blocked-products"></a>Ändra lagringsdimensionsgruppen för spärrade produkter 
 
Artiklar som ska användas som en del av lagerstyrningsprocesser måste associeras med en lagringsdimensionsgrupp där platslagerdimensionen är aktiv och där parametern **Använd lagerstyrningsprocesser** väljs. När du väljer den här inställningen aktiveras lagerdimensionerna för plats, lagerställe, lagerstatus, plats och registreringsskylt.

Om du vill upphäva blockeringen av produkter som blockerades under uppgraderingen måste du välja en ny lagringsdimensionsgruppen för produkterna. Observera att du kan ändra lagringsdimensionsgruppen även om det finns öppna lagertransaktioner. Om du vill använda artiklar som har blockerats under uppgraderingen har du två möjligheter:

-   Ändra lagringsdimensionsgruppen för artikeln till en lagringsdimensionsgrupp som endast använder plats, lagerställe och platslagerdimensioner. Ändringen innebär att lagerdimensionen lastpalls-ID inte längre används.
-   Ändra lagringsdimensionsgruppen för artikeln till en lagringsdimensionsgrupp som endast använder lagerstyrningsprocesser. Ändringen innebär att lagerdimensionen registreringsskylt används nu.

## <a name="configure-warehouse-management-processes"></a>Konfigurera lagerstyrningsprocesser
Innan du kan använda frisläppta produkter i **lagerstyrningsmodulen** måste produkterna använda en lagringsdimensionsgrupp där parametern **Använd lagerstyrningsprocesser** väljs.

### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Aktivera lagerställen för att använda lagerstyrningsprocesser

1.  Skapa minst en ny platsprofil.
2.  Klicka på **Lagerstyrning** &gt; **Inställningar** &gt; **Aktivera lagerstyrningsprocesser** &gt; **Aktivera inställning av lagerställe**.
3.  På sidan **Aktivera inställning av lagerstyrning** kan du lägga till de lagerställen som ska aktiveras. Du kan slutföra det här steget antingen direkt på sidan eller genom att använda Microsoft Office-integreringen.
4.  Tilldela en platsprofil till alla platser. Du kan enkelt slutföra det här steget genom att använda Microsoft Office-integreringen direkt från sidan. Du kan antingen exportera och importera data, eller använda dataenheten i [Datahantering](../../dev-itpro/data-entities/data-entities.md).
5.  Godkänn ändringarna. Som en del av valideringen kan olika valideringar av dataintegritet uppträda. Som en del av en större uppgraderingsprocess kan problem som uppstår justeras på källimplementeringen. I detta fall krävs ytterligare en datauppgradering.
6.  Behandla ändringarna.

### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Ändra lagringsdimensionsgruppen för artiklar, så att den använder lagerstyrningsprocesser

1.  Skapa ett nytt värde för **Lagerstatus** och tilldela det som **Status-ID för lager som standard** i inställningarna för **Lagerstyrningsparametrar**.
2.  Skapa en ny lagringsdimensionsgrupp där parametern **Använd lagerstyrningsprocesser** väljs.
3.  På sidan **Reservationshierarki** kan du definiera en ny reservationshierarki enligt artikelns lagring och spårningsdimensionsgrupper.
4.  Skapa minst en eller flera sekvensgrupper som inkluderar minst samma enheter som används för artikelns lagerenheter.
5.  Klicka på **Lagerstyrning** &gt; **Inställningar** &gt; **Aktivera lagerstyrningsprocesser** &gt; **Ändra lagringsdimensionsgrupp för artiklar**.
6.  På sidan **Ändra lagringsdimensionsgruppen för artiklar** och lägg till artikelnummer, lagringsdimensionsgrupper och sekvensgrupper. Du kan slutföra det här steget direkt på sidan med hjälp av Microsoft Office-integrering eller genom att använda dataenhetsprocessen i [Datahantering](../../dev-itpro/data-entities/data-entities.md).
7.  Godkänn ändringarna. Som en del av valideringen kan olika valideringar av dataintegritet uppträda. Som en del av en större uppgraderingsprocess kan problem som uppstår justeras på källimplementeringen. I detta fall krävs ytterligare en datauppgradering.
8.  Behandla ändringarna. En uppdatering av alla lagerdimensioner kan ta en stund. Du kan övervaka förloppet med hjälp av batchjobbsuppgifterna.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]