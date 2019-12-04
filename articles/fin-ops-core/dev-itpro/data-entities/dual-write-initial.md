---
title: Exekveringsorder för initial synkronisering av Finance and Operations-appar och Common Data Service
description: Det här avsnittet anger ordningen för synkroniseringen som du måste följa för att skapa de ursprungliga data.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: cf444ef1192fed3a6a49282da37374dd8c443356
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769647"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a>Exekveringsorder för initial synkronisering av Finance and Operations-appar och Common Data Service

[!include [banner](../includes/banner.md)]

Innan du använder dataintegrering måste du skapa de ursprungliga data som krävs för kunder, leverantörer och kontakter. Du vill till exempel skapa en ny **leverantörsgruppartikel** och ange värdet för **betalningsvillkor** till **Net30.** I det här fallet måste du, innan du försöker skapa artikeln **leverantörsgrupp**, se till **Net30** finns i både appen och Common Data Service. (I framtiden kommer Microsoft att släppa en funktion för dubbelriktad skrivning som kallas initial synkronisering. Den kommer att göra en engångsdatasynkronisering mellan appen och Common Data Service som en del av inställningen dubbelriktad skrivning.)

> [!TIP]
> Microsoft släpper en karta för dubbelriktad skrivning för alla referensdata, inklusive **Betalningsvillkor** (betalningsvillkor). Om du redan har de ursprungliga data i ett system kan en liten uppdateringsåtgärd på en post utlösa dubbel-skriv på posten.

Du måste följa följande prioritetsordning och kontrollera att de ursprungliga data är tillgängliga i appen och Common Data Service.

## <a name="vendor"></a>Leverantör

Här är ordningsföljden för entiteten **Leverantör**:

1. Leverantörsgrupp

    1. Betalningsvillkor

        1. Betalningsdag och rader
        2. Betalningsplan

2. Betalningsmetod för leverantör

## <a name="customer-organization"></a>Kund (organisation)

Här är ordningsföljden för entiteten **Kund**:

1. Kundgrupp

    1. Betalningsvillkor

        1. Betalningsdag och rader
        2. Betalning 

2. Kundbetalningsmetod

## <a name="contact-person"></a>Kontakt (person)

Här är ordningsföljden för entiteten **Kontakt**:

1. Kund
2. Leverantör
