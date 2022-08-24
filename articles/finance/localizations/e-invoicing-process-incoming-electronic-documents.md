---
title: Bearbetning av inkommande elektroniska dokument
description: Detta ämne ger en översikt över bearbetningen av inkommande elektroniska dokument.
author: gionoder
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 554bc8fde3b2135eb878d885541c76ecd6d66493
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277314"
---
# <a name="processing-of-incoming-electronic-documents"></a>Bearbetning av inkommande elektroniska dokument

[!include [banner](../includes/banner.md)]

Inkommande elektroniska dokument, till exempel elektroniska leverantörsfakturor, kan importeras och bearbetas på två sätt:

- Filerna hämtas från externa kanaler och skickas direkt till ditt anslutna program. Där genomgår de ytterligare omvandling och importeras sedan till databasen.
- Filerna genomgår förbearbetning i e-faktureringstjänsten och skickas sedan till ditt anslutna program.

e-fakturering stöder två kanaler för inkommande dokument: e-post och Microsoft SharePoint-mappar.

Det finns inställningstyper som anger huruvida dokument genomgår förbearbetning eller skickas direkt till ditt anslutna program:

- **Datakanal** – Systemet skickar dokumentet direkt till det anslutna programmet.
- **Datakanal med bearbetningspipeline** – Du kan ställa in ytterligare åtgärder som ska köras innan dokumentet överförs till det anknutna programmet.

Information om hur du ställer in scenarier för bearbetning av inkommande elektroniska dokument för de olika kanalerna finns i [Konfigurera en e-postkanal](e-invoicing-configure-email.md) och [Konfigurera en SharePoint-kanal](e-invoicing-configure-sharepoint-channel.md).
