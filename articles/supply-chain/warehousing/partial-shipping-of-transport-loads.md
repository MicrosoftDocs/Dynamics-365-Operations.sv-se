---
title: Delleverans av en transportlast
description: "Det här avsnittet beskriver hur du delvis levererar en last och skjuter upp planering av kapacitet för lasten."
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2a1fb66ddb956b9e248ebc6ca6cf71d7b32b4705
ms.openlocfilehash: 77b713e7d55e06c89dd175dfea7e7ade9734b656
ms.contentlocale: sv-se
ms.lasthandoff: 04/09/2018

---

# <a name="partial-shipment-of-a-transport-load"></a>Delleverans av en transportlast

[!include[banner](../includes/banner.md)]

Genom att ställa in en delleverans av last kan du hantera laster där kapaciteten inte kan bestämmas förrän alla försäljningsrader har lagts till en last. Processen kan sedan slutföras när man vet exakt antal lastpallar. Därför behöver du inte bestämma vilka lastpallar som ska tilldelas till vilket transport tills det ögonblick då en transport fysiskt lastas ur mellanlagret.

Den här funktionen är ett praktiskt alternativ för kontroll av fastare struktur där måste du bestämma vilka lastpallar som tilldelas vilken transport före plockning av arbete eller lastning av arbetet kan skapas. Däremot kan användare konfigurera individuella laster för en bekräftelse av delleverans. Transportlastningsprocessen för dessa laster kan sedan uppstå. Därför kan transportplaneringsavdelningen planera laster utan att behöva tänka på kapacitet för enskilda transporter.

Vid lastningen kan arbetarna definiera nya transportlaster som en lastpall kan lastas på. De kan också se en befintlig transportlast. Dessa data kan registreras av en mobil enhet. Därför kan flera lagerarbetare lasta lager från samma laster eller olika laster på samma lastbil. Lasterna kan sedan helt eller delvis levereras.

> [!NOTE] 
> För att kunna lasta lager från en last till en specifik transportlast och skicka lasten måste arbete genereras med hjälp av en lastningsklass i en arbetsmall. Vanlig plockning av typen **plockning** kan inte lastas på en transportlast på till exempel en lastbil.

## <a name="set-up-transport-loads-for-partial-shipment"></a>Ange transportlast för en delleverans

Inställningen för delleveranser av last består av följande två procedurer.

### <a name="set-the-loading-strategy"></a>Ange lastningsstrategi

Du måste aktivera delvis lastning genom att ange lastningsstrategin. Du kan ange lastningsstrategin när du har skapat en last.

1. Välj **Lagerstyrning**\>**Laster**\>**Alla laster**.
2. Välj en last och klicka sedan på **Rubrik**.
3. I fältet **Lastningsstrategi**, välj **Partiell leverans av last tillåts**.

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a>Skapa ett menyalternativ för lasting av transportlaster

Du måste skapa ett nytt menyalternativ som kan transportera laster som ska lastas. En transportlast låter dig gruppera rader från en last till flera laster. Allt som läggs till transportlasten kan sedan skickas med en mobilskanner.

1. Välj **Lagerstyrning** \> **InställningarSetup** \> **Mobil enhet** \> **Menyalternativ på mobil enhet**.
2. Markera **Ny** och sedan, i fältet **Läge**, markerar du **Arbete**.
3. Ange alternativet **Använd befintligt arbete** till **Ja**.
4. På fliken **Allmänt** i fältet **Dirigerad av**, välj **Transportlastning**.
5. Aktivera leveransbekräftelse på en mobilskanner i fältet **Tillåten leveransbekräftelsetyp** och välj **Transportlast**.

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a>Bekräfta leveransen av en transportlast från klienten

Denna inställning låter dig bekräfta en transportlast som inkluderar full last eller delvis lastad last som ska levereras.

1. Välj **Lagerstyrning**\>**Laster**\>**Transportlaster**.
2. I Åtgärdsfönster, på fliken **Leverera och ta emot** i gruppen **Bekräfta**, välj **Transport**.

