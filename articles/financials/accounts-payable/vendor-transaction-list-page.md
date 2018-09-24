---
title: "Leverantörstransaktionssida"
description: "Det här avsnittet innehåller information om leverantörstransaktionssidan för Microsoft Dynamics 365 for Finance and Operations."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 1ef7d97f059801f2fb2c0d451546b57055208f81
ms.contentlocale: sv-se
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-transaction-list-page"></a>Leverantörstransaktionssida

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Visa kvittningar

Fliken **Visa kvittningar** i åtgärdsfönstret ger snabb tillgång till kvittningshistoriken och mer information om hela kvittningstransaktionen. Du kan också visa ytterligare transaktioner som är relaterade till den valda transaktionen, antingen eftersom de tillhörde samma kvittning eller eftersom de är betalningar som skapades i samma betalningsjournal.

1. Välj **Leverantörsreskontra \>Alla leverantörer**.
2. Markera en leverantör som har transaktioner och välj **Leverantör \>Transaktioner**.
3. Välj en transaktion som du vill undersöka.
4. Välj fliken **Visa kvittningar** i åtgärdsfönstret.

    Dialogrutan **Visa kvittningar** öppnas och visar den valda transaktionen och alla dokument som kvittas mot den. Denna dialogruta liknar kvittningshistorikvyn, men den innehåller alla relaterade dokument.

5. Du kan utföra olika uppgifter från den här dialogrutan. Markera en eller flera verifikationer och välj en av följande menyer:

   - **Visa redovisning** – Alla verifikationer som är relaterade till de valda dokumenten visas. Välj **Stäng** för att stänga dialogrutan.
   - **Exportera** – Exportera de valda verifikationerna till Microsoft Excel.
   - **Visa relaterade betalningar** – Alla transaktioner i betalningsjournal som skapades i betalningsjournalen som är relaterade till det valda dokumentet visas. Dessutom visas alla kvittningar som är relaterade till betalningarna. Etiketten över denna many ändras till **Visa kvittningar**. Välj **Visa kvittningar** om du endast vill visa transaktioner som visades när du öppnade dialogrutan **Visa kvittningar**.
    - **Kvitta transaktioner** – Denna meny visas om det ursprungliga dokumentet som valdes inte kvittats helt. När du väljer den visas dialogrutan **kvitta transaktioner** där du kan välja transaktioner för kvittning.
    - **Ångra kvittningar** – Denna meny visas om det ursprungliga dokumentet som valdes inte kvittats helt. När du väljer den visas dialogrutan **Ångra kvittningar** där du kan ångra kvittningar som har gjorts för det dokumentet.

