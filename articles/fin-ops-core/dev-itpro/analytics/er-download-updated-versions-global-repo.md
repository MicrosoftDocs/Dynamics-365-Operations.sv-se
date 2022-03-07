---
title: Importera uppdaterade versioner av ER-konfigurationer
description: I det här avsnittet beskrivs hur du importerar uppdaterade versioner av konfigurationer av elektronisk rapportering (ER) från den globala lagringsplatsen för konfigurationstjänsten.
author: NickSelin
manager: AnnBe
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 0c65315c4fa6a42b4bbb0d008b58f8df9cc0ea3d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561888"
---
# <a name="import-updated-versions-of-er-configurations"></a>Importera uppdaterade versioner av ER-konfigurationer

[!include [banner](../includes/banner.md)]

Elektronisk rapportering (ER) [databaser](general-electronic-reporting.md#Repository) används för att dela [ER-konfigurationer](general-electronic-reporting.md#Configuration). Du kan [Importera](download-electronic-reporting-configuration-lcs.md) ER-konfigurationer från olika databaser till din instans av Microsoft Dynamics 365 Finance. När du importerar ER-konfigurationer kan [konfigurationsprovidern](general-electronic-reporting.md#Provider) publicera nya databaser för [versioner](general-electronic-reporting.md#component-versioning) så att de kan delas.

I det här avsnittet beskrivs hur du importerar uppdaterade versioner av ER-konfigurationer från den globala lagringsplatsen för konfigurationstjänsten. Mer information finns i [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, konfigurationstjänst](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="review-the-available-updated-versions"></a>Granska tillgängliga uppdaterade versioner

1. Logga in på Finance med någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Importera uppdateringar av konfigurationsversioner**.

    ![Sidan lokaliseringskonfigurationer](./media/er-download-updated-versions-global-repo1.png)

4. I dialogrutan **Importera uppdateringar av konfigurationsversioner för elektronisk rapportering** i fältet **Körläge** välj **Visa endast tillgängliga uppdateringar**. Välj sedan **OK**. 

    ![Fältet körläge är inställt på att endast visa tillgängliga uppdateringar](./media/er-download-updated-versions-global-repo2.png)

5. Granska de meddelanden som du får. Dessa meddelanden innehåller följande information om ER-konfigurationer i den aktuella Finance-instansen och hur de jämförs med innehållet i den globala databasen:

    - Totalt antal ER-konfigurationer
    - ER-konfigurationer som inte finns i den globala databasen
    - ER-konfigurationer för vilka den senaste versionen redan finns tillgänglig i den aktuella Finance-instansen (om du vill visa den fullständiga listan med dessa ER-konfigurationer väljer du länken **Meddelandeinformation** .)

        ![Meddelandet "De senaste versionerna av följande konfigurationer har redan importerats" och meddelandeinformation](./media/er-download-updated-versions-global-repo3.png)

    - ER-konfigurationer för vilka den senaste versionen finns tillgänglig i den globala databasen kan importeras till den aktuella Finance-instansen (om du vill visa den fullständiga listan med dessa ER-konfigurationer väljer du länken **Meddelandeinformation** .)

        ![Meddelandet "Tillgängliga uppdateringar" och meddelandeinformation](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a>Importera tillgängliga uppdaterade versioner

1. Logga in på Finance med någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Importera uppdateringar av konfigurationsversioner**.
4. I dialogrutan **Importera uppdateringar av konfigurationsversioner för elektronisk rapportering** i fältet **Körläge** väljer du **Importera senaste uppdateringar** för att importera de senaste versionerna av ER-konfigurationer från den globala databasen till den aktuella Finance-instansen.
5. Om du vill tidsplanera ett batchjobb för importen, på snabbfliken **Kör i bakgrunden** anger du alternativet **Batchbearbetning** till **Ja**. Om du vill upprepa importen regelbundet måste du konfigurera den nödvändiga återupprepningen.

    ![Fältet körläge har angetts för import av de senaste uppdateringarna](./media/er-download-updated-versions-global-repo5.png)

6. Välj **OK**.
7. Gör något av följande om du vill veta vilka konfigurationsversioner som har importerats:

    - Om du kör importen interaktivt i stället för att använda ett batchjobb kan du granska de meddelanden som du får.

        ![Mottagna meddelanden under en interaktiv importkörning](./media/er-download-updated-versions-global-repo6.png)

    - Gör så här om du kör kommandot Importera i batchläge:

        1. Gå till **Vanlig** \> **Förfrågningar** \> **Batchjobb** \> **Mina batchjobb**.
        2. Sök och markera jobbet **Importera uppdateringar av konfigurationsversioner för elektronisk rapportering** och sedan i åtgärdsfönstret väljer du fliken **Batchjobb**, välj **Historik över batchjobb** för att visa jobbhistoriken.
        3. På sidan **Historik över batchjobb**, välj **Logg**. I meddelandet som du tar emot väljer du länken **Meddelandeinformation** för att visa jobbloggen.

        ![Jobblogg](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> Vi rekommenderar inte att du schemalägger ett återkommande batchjobb för att importera uppdaterade versioner av ER-konfigurationer direkt från den globala databasen till en produktionsmiljö, eftersom de importerade versionerna omedelbart kommer att vara tillgängliga för användning. Använd i stället den här metoden för att distribuera versioner av ER-konfigurationer till en begränsad miljö. De kan sedan utvärderas i begränsat läge innan de distribueras till en produktionsmiljö.

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]