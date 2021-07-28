---
title: Konfigurera SQL Server Reporting Services för lokal distribution
description: Det här avsnittet innehåller information om hur du konfigurerar SQL Server Reporting Services (SSRS) för en lokal distribution.
author: PeterRFriis
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: peterfriis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: e8046ce0926a4da6c20b4beb28b4e10aa3fa054c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344916"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a>Konfigurera SQL Server Reporting Services för lokal distribution

[!include [banner](../includes/banner.md)]

Använd stegen i det här avsnittet för att konfigurera SQL Server Reporting Services (SSRS) för din Microsoft Dynamics 365 Finance + Operations (lokala) distribution.

1. Öppna Reporting Services Configuration Manager-programmet.
2. Lämna standardnamnet **servernamn**, som bör vara namnet på den aktuella datorn och **rapportserverinstansen**, **MSSQLSERVER**.
3. Klicka på **anslut**.

    [![Konfigurationsanslutning för rapporteringsserver.](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)

4. Klicka på fliken **tjänstkonto** och verifiera att inställningarna stämmer med bilden nedan.

    [![Fliken Tjänstekonto.](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)

5. Klicka på fliken **Webbtjänst-URL** och verifiera att inställningarna stämmer med bilden nedan.

    [![Fliken Webbtjänst-URL.](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)

6. Klicka på fliken **database** och kontrollera att den **databasnamn** och **inställning av autentiseringsuppgifter** matchar följande bild.

    > [!NOTE]
    > Du behöver skapa en ny databas. För att göra detta klickar du på **ändra databasen** och kontrollerar att det nya databasnamnet är: **DynamicsAxReportServer**.

    [![fliken Databas.](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)

7. Klicka på fliken **Webbportal-URL** och verifiera att inställningarna stämmer med bilden nedan.

    > [!NOTE]
    > Du måste klicka på **Använd** för att skapa och konfigurera portalen.

    [![fliken Webbportal-URL.](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)

    När portalen har konfigurerats kommer fliken **webbportal** att matcha följande bild.

    [![fliken Webbportal.](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)

8. Klicka på rapport-URL om du vill visa webbportalen SQL Server Reporting Services.
9. När du är på portalen kan du skapa en ny mapp med namnet **Dynamics**.

    [![mappen Dynamics.](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)

10. I **Reporting Services Configuration Manager** klickar du på fliken **E-postinställningar** och verifierar att inställningarna stämmer med bilden nedan.

    [![fliken e-postinställningar.](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)

11. Klicka på fliken **Körningskonto** och verifiera att inställningarna stämmer med bilden nedan.

    [![fliken Körningskonto.](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)

    Ändra inte standardinställningarna på fliken **krypteringsnycklar**.

    [![fliken Krypteringsnycklar.](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)

12. Klicka på fliken **Abonnemangsinställningar** och verifiera att inställningarna stämmer med bilden nedan.

    [![fliken Abonnemangsinställningar.](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)

    Ändra inte standardinställningarna på fliken **Skala ut-distribution**.

    [![fliken Skala upp distribution.](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)

    Ändra inte standardinställningarna på fliken **Power BI Integration**.

    [![fliken Power BI-integrering.](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)

13. Klicka på **Avsluta** för att stänga **Reporting Services Configuration Manager**.

    [![stäng konfigureringsverktyget för rapporteringstjänster.](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
