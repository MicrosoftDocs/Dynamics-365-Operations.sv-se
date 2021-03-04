---
title: Översikt över kanaler
description: Det här ämnet innehåller en översikt över kanaler i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 099ccd9f769ea5c431c1a82532d8654cbbd082b1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415792"
---
# <a name="channels-overview"></a>Översikt över kanaler


[!include [banner](includes/banner.md)]

Det här ämnet innehåller en översikt över kanaler i Microsoft Dynamics 365 Commerce. Här finns information om de uppgifter du måste utföra båda före och efter att du ställer in varje kanal.

## <a name="types-of-channels"></a>Typer av kanaler

Dynamics 365 Commerce har stöd för tre olika kanaltyper: butik, kundtjänst och onlinekanaler.

### <a name="retail-channels"></a>Butikskanaler

Butikskanaler utgör fysiska standardbutiker. Varje butik kan ha egna kassaregister (POS), intäkts- och utgiftskonton och personal. 

### <a name="call-center-channels"></a>Kundtjänstkanaler

Kundtjänstkanaler representerar kundtjänstorder och kundhantering.

### <a name="online-channels"></a>Onlinekanaler

Online-kanaler representerar onlinebutiker. När en onlinekanal har skapats måste en webbplats skapas med hjälp av Microsoft Dynamics 365 Commerce verktyg för webbplatsskapare eller någon annan näthandelslösning från tredje part.

## <a name="channel-setup-basics"></a>Grundläggande kanalinställningar

Konfigurera kanaler utförs i handelsverktyget. Varje kanal kan ha sina egna betalningsmetoder, prisgrupper, produktvarianter, sortiment och produktuppsättningar. När du har skapat en kanal tilldelar du produkter som du vill ha och sälja i butiken. Varje kanaltyp har en unik uppsättning funktioner som kan behöva konfigureras. Till exempel behöver en butikskanal tilldelade medarbetare, register och kunder. När en ny kanal har skapats måste den tilldelas en organisationshierarki.

## <a name="channel-setup-prerequisites"></a>Förutsättningar för att ställa in kanaler

Innan du kan ställa in en kanal måste du slutföra några nödvändiga uppgifter baserade på kanaltypen. Mer information finns i [krav för kanalinställning](channels-prerequisites.md).

## <a name="set-up-a-channel"></a>Ställ in en kanal

När du har slutfört nödvändiga uppgifter kan du använda följande länkar för ytterligare installationsanvisningar.

- [Ställa in en butikskanal](channel-setup-retail.md)
- [Ställa in en kundtjänstkanal](channel-setup-callcenter.md)
- [Ställ in en onlinekanal](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a>Ytterligare resurser

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)

[Ställa in en butikskanal](channel-setup-retail.md)
    
[Ställ in en onlinekanal](channel-setup-online.md)

[Ställa in en kundtjänstkanal](channel-setup-callcenter.md)

[Ange organisationshierarkier](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]