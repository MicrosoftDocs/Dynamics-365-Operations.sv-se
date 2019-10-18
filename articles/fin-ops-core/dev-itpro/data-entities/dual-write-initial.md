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
ms.openlocfilehash: 3110cb809558d168e9d97f640701b249caf73f6c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184518"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a>Exekveringsorder för initial synkronisering av Finance and Operations-appar och Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

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
