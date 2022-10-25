---
title: Avancerade inställningar för lösning för Invoice Capture
description: Den här artikeln innehåller information om avancerade inställningar i lösningen Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: a1e24b700d0f30fd90f2619dd6e6687736a86774
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691204"
---
# <a name="invoice-capture-solution-advanced-settings"></a>Avancerade inställningar för lösning för Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Den här artikeln innehåller information om avancerade inställningar i lösningen Invoice Capture.

## <a name="create-additional-connections-for-channels"></a>Skapa ytterligare anslutningar för kanaler

Du måste skapa anslutningar till e-post eller fillagring för att aktivera övervakning av inkommande fakturor från olika kanaler. Du måste registrera anslutningar i början för att bevilja åtkomst till automatiska flöden som används i lösningen.

Följande anslutningstyper används för att importera fakturor:

- Office 365 Outlook
- Outlook.com
- OneDrive
- SharePoint

Kanalen för fakturaimport använder anslutningarna i ytterligare konfigurationssteg. Innan användare kan skapa en kanal med en specifik anslutning måste säkerhetsrollen **administratör** tilldelas dem, och de måste skapa anslutningar.

Gör så här om du vill skapa en anslutning till Microsoft Dataverse.

1. Gå till **Administratörssystem \> Standardlösning**.
2. Markera **Ny** och välj sedan **Anslutningsreferens**.
3. Ange ett namn i fältet **Visningsnamn**.
4. Välj **Microsoft Dataverse** som anslutningsprogram.
5. Om du ställer in anslutningen för första gången väljer du **Ny anslutning**.
6. I dialogrutan som visas, skapa en Dataverse anslutning och välj **Skapa**.
7. Ange Dataverse-konto och lösenord.
8. När valideringen är godkänd går du till anslutningssidan, väljer **Uppdatera**, väljer kontot och sedan **Skapa**.

Följ dessa steg för att skapa en e-post- eller fillagringsanslutning.

1. På sidan **Skapande av anslutning** i fältet **Anslutningstyp**, välj **Office 365 Outlook**.
2. Om du vill ha en e-postanslutning väljer du **Outlook.com** eller **Office 365 Outlook** som anslutning. Du kan välja en eller flera för en fillagringsanslutning **OneDrive** eller **SharePoint**.

Om du vill granska befintliga anslutningar går du till **Standardlösning \> Objekt \> Anslutningsreferens**. Användaren som skapar kanaler bör ha minst en Dataverse anslutning utöver specifika e-post- eller fillagringsanslutningar. Den nya kanalens skapare ska vara ägare till anslutningen.
