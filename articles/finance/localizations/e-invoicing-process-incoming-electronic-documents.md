---
title: Bearbetning av inkommande elektroniska dokument
description: Detta ämne ger en översikt över bearbetningen av inkommande elektroniska dokument.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: dec4c16c8ba9f0ba55f30f3944eff172cf9db724
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910020"
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
