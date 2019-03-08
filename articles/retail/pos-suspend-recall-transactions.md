---
title: Pausa och återuppta en transaktion i kassan
description: Det här avsnittet beskriver hur användare kan avbryta pågående transaktioner och sedan återuppta dem senare eller i en annan kassa med Microsoft Dynamics 365 for Retail.
author: jblucher
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ffb04609318c7de4b9ef729a8e03a7f9395806b8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "333908"
---
# <a name="suspend-and-resume-transactions-in-the-point-of-sale-pos"></a>Pausa och återuppta transaktioner i kassan

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Kassaanvändare kan avbryta pågående transaktioner och återuppta dem senare, eller i en annan kassa. Transaktioner avbryts ofta för att snabbt frigöra en kassa för en annan uppgift utan att förlora några framsteg på den aktuella transaktionen. Till exempel n butiksmedarbetare påbörjar behandlingen av en kundtransaktion på en mobil enhet men måste utföra i en kassa med en kassalåda. I det här fallet kan butiksmedarbetaren pausa transaktionen på mobilenheten och sedan återkalla och återuppta den i en kassa.

## <a name="configure-suspend-and-resume-functionality"></a>Konfigurera funktioner för att pausa och återuppta

### <a name="pos-operations"></a>POS-operationer

Två [kassaoperationer](pos-operations.md) låter kassan ge stöd för att pausa och återuppta scenarier. Du kan tilldela dessa operationer som [knappsatser](pos-screen-layouts.md) på transaktionssidan eller välkomstsidan.

- 503: Pausa transaction
- 504: Återkalla transaktion

### <a name="receipt-template"></a>Kvittomall

Kassan kan konfigureras för att generera ett utskrivet kvitto om en transaktion avbryts. Detta kvitto kan sedan användas för att snabbt identifiera och återkalla transaktionen senare.

Om du vill aktivera kassan att skriva ut ett kvitto måste du lägga till kvittoformatet **Pausad transaktion** till butikens kvittoprofil. Du kan utforma kvittoformatet så att det omfattar eller utelämnar specifik information om transaktionen. Formatet kan exempelvis innehålla en streckkod för skanning.

### <a name="receipt-numbering"></a>Kvittonumrering

När det gäller andra kassatransaktionstyper som genererar ett utskrivet kvitto kan du definiera en nummerserie för pausade transaktioner i avsnittet **Kvittonumrering** i butikens funktionsprofil.

### <a name="void-when-closing-shift"></a>Annullera vid skiftstängning

Du kan använda alternativet **Annullera vid skiftstängning** för att kräva att användare antingen måste slutföra eller annullera alla pausade transaktioner innan de har avslutar sina skift. Under operationen **Avsluta skift** uppmanar kassan användare att visa eller annullera alla utestående pausade transaktioner.

## <a name="suspend-and-resume-a-transaction"></a>Pausa och återuppta en transaktion

### <a name="suspend-a-transaction"></a>Pausa en transaktion

Användare som har behörighet och som har en skärmlayout med operationen **Pausa transaktion** kan pausa en transaktion så att den kan återställas senare eller i en annan kassa.

Transaktioner kan endast pausas om de **inte** innehåller följande typer av rader:

- Aktiva betalningsrader
- Presentkortrader (antingen utfärda ett presentkort eller lägga till presentkortets saldo)

En pausad transaktion påverkar inte försäljningsinformation eller lagertillgänglighetsinformation för butiken.

### <a name="resume-a-suspended-transaction"></a>Återkalla en pausad transaktion

Pausade transaktioner kan återkallas och återuppta i samma butik av alla användare som har tillräcklig behörighet och som även har en layout som innehåller operationen **återkalla transaktion**.

För att snabbt och enkelt återkalla en pausad transaktion, skanna streckkoden på den utskrivna bilden medan du tittar på listan över transaktioner från operationen **återkalla transaktion**.

### <a name="considerations-for-offline-mode"></a>Att tänka på vid offlineläge

- En transaktion som avbryts när kassan är i online-läge kan inte återupptas i offlineläge eftersom data inte synkroniseras till offlinedatabasen.
- Om du pausar en transaktion när kassan är offline, kan du återkalla den i offlineläge under förutsättning att kassan inte växlar tillbaka till onlineläge när som helst när du inaktiverar transaktionen. När kassan ändras tillbaka till online-läge, flyttas data om pausade transaktioner till onlinedatabasen och tas bort från offlinedatabasen. Transaktionerna kan därför bara återupptas i online-läge. Om du ändrar tillbaka kassan till offlineläge kan du inte återuppta den pausade transaktionen eftersom den redan har tagits bort från offlinedatabasen.

### <a name="void-a-suspended-transaction"></a>Annullera en pausad transaktion

Du kan annullera pausade transaktioner antingen genom att återkalla transaktionen och sedan utföra operationen **Annullera transaktion**, eller genom att välja transaktionen i listan **återkalla transaktion** och välja **annullera** i appfältet. Alternativt kan butiken konfigureras för att uppmana användare att annullera pausade transaktioner när de har avslutat sina skift.
