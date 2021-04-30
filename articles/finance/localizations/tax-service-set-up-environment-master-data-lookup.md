---
title: Ställa in en miljö för att söka efter huvuddata
description: I det här avsnittet beskrivs hur du ställer in din miljön att använda sökfunktionen huvuddata för skatteberäkning.
author: kai-cloud
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eda093a75898bace2f3c7968933b83ccafa7fabb
ms.sourcegitcommit: 66095f1b7e0fd2756aa29fd7deb9ce5392b7e0b2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2021
ms.locfileid: "5869100"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Ställa in en miljö för att söka efter huvuddata

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs hur du ställer in din miljön att använda sökfunktionen huvuddata för skatteberäkning.

1. Konfigurera Power Platform-integrering i Lifecycle Services (LCS). Mer information finns i [Microsoft Power Platform-integrering - tilläggsöversikt](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
2. Konfigurera Dynamics 365 Finance och Microsoft Dataverse. Mer information finns i [Skaffa lösningen](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) samt i [Autentisering och auktorisering](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
3. Importera *Virtuell entitetslösning för erforderlig skattetjänst* från [Virtuell entitet för skattetjänst](https://go.microsoft.com/fwlink/?linkid=2158160).
4. Konfigurera Dynamics 365 Regulatory Configuration Service (RCS). 
5. Skapa en tjänstebegäran för Microsoft i syfte att aktivera förhandsversioner av följande funktioner:

      - ERCdsFeature
      - TaxServiceCDSFeature

6. I arbetsytan **Funktionshantering** aktiverar du följande funktioner:

      - (Förhandsgranskning) Dataverse-datakällor för elektronisk rapportering
      - (Förhandsversion) Stöd för Dataverse-datakällor
      - (Förhandsversion) Globaliseringsfunktioner

5. Logga in på RCS med hjälp av ett admin-konto för klientorganisation.
6. Gå till **Elektronisk rapportering** > **Anslutna program**. 
7. Om du vill lägga till en post, välj **Ny** och ange följande fältinformation. 

   - Ange sedan ett namn i fältet **Namn**.
   - I fältet **Typ** väljer du **Dataverse**.
   - I fältet **Program** anger du din Dataverse-URL.
   - I fältet **Klientorganisation** anger du din klientorganisation.
   - I fältet **Anpassad URL** anger du din Dataverse-URL och tillägger "/api/data/v9.1".

8. Välj **Kontrollera anslutning** och slutför anslutningsprocessen. 

   [![Knappen Kontrollera anslutning](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

9. Gå till **Elektronisk rapportering** > **Skattekonfigurationer** och importera skattekonfigurationer från [Skattekonfigurationer](https://go.microsoft.com/fwlink/?linkid=2158352).

   [![Sidan Skattekonfigurationer, modellträd för skattedata](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

10. Gå till **Modellmappning för beskattningsbart dokument** eller **Modellmappning för Dataverse** om du använder en Microsoft-konfiguration, och i fältet **Anslutet program** väljer du sedan den post som du skapade i steg 7.
11. Ange **Standard för modellmappning** som **Ja**.

   [![Modellmappningssida](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
