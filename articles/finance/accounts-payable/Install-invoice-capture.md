---
title: Installera lösningen för Invoice Capture
description: I den här artikeln finns information om hur du installerar lösningen Invoice Capture och integrera den med Microsoft Dynamics 365 Finance.
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
ms.openlocfilehash: d853e347c833345f34b65760fd7ee35cbb38c9a3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691225"
---
# <a name="install-the-invoice-capture-solution"></a>Installera lösningen för Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Om du har installerat lösningen i privat förhandsgranskning måste du avinstallera den gamla lösningen innan du fortsätter.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan installera lösningen Invoice Capture måste du slutföra följande förutsättningar:

1. Registrera ett program och lägg till en klienthemlighet i Microsoft Azure Active Directory (Azure AD) under ditt Azure-abonnemang. Mer information finns i [Registrera en webbapp med AAD](../../dev-itpro/data-entities/services-home-page.md#register-a-web-application-with-aad).

    > [!NOTE]
    > Notera **ID för program (klient)**, **Klienthemlighet** och **ID för klientorganisation**, detta eftersom du behöver dem senare.

2. Registrera Azure-programmet i en Dynamics 365 Finance-miljö. Mer information finns i [Registrera ditt externa program](../../dev-itpro/data-entities/services-home-page.md#register-your-external-application).

## <a name="install-and-set-up-the-solution"></a>Installera och konfigurera lösningen

Om du vill installera lösningen Invoice Capture, gå till AppSource och välj länken för förhandsgranskningsversionen av [Dynamics 365 Invoice Capture](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics365-invoice-capture-preview?flightCodes=invoicecapture). När installationen är klar visas lösningen som har installerats i den valda miljön i Power Apps.

Om du vill slutföra denna inställning, följ dessa steg.

1. Hämta den [medhjälparlösningen](https://github.com/InvoiceCapture/InstallationTools/releases/download/latest/msdyn_InvoiceCaptureIntallationTools.zip) för att ställa in följande detaljer:

    - Kommunikationen mellan Microsoft Power Platform och ekonomimiljön
    - Anslutningsreferensen för Dataverse och Office 365 Outlook som kommer att användas av kanalen

2. I Power Apps, gå till din miljö och välj **importlösning**.
3. Välj **Bläddra**, välj lösningspaketet för medhjälpare som du hämtat och välj sedan **Nästa**.
4. Välj **Nästa**.
5. Tilldela en befintlig anslutning eller skapa en ny genom att välja **Ny anslutning**.
6. När paketet har importerats öppnar du **Dynamics 365 Invoice Capture – Installationsverktyg**.
7. Kör molnbaserade flödet för att ställa in anslutningen mellan lösningen Invoice Capture i Microsoft Power Platform och Ekonomi.
8. Välj **Kör** och ange följande parametrar:

    - **Dynamics 365 Finance Url** – URL:en för den ekonomimiljö som du vill integrera med.
    - **Klientorganisations-ID** – Klientorganisations-ID för ekonomimiljön.
    - **Klient-ID** – Det Azure-program-ID som har registrerats.
    - **Klienthemlighet** – Klienthemligheten som genererades för Azure-appen.
