---
title: Konfigurera tjänst-till-tjänst-autentisering
description: Denna artikel beskriver hur du konfigurerar autentisering tjänst-till-tjänst i Microsoft Dynamics 365 Commerce för säkra API-anrop för värderingar och granskningar.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: e3134d4ddb2e4f3d260e51d49e7399ff84e0d74a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279459"
---
# <a name="configure-service-to-service-authentication"></a>Konfigurera tjänst-till-tjänst-autentisering

[!include [banner](includes/banner.md)]

Denna artikel beskriver hur du konfigurerar autentisering tjänst-till-tjänst (S2S) i Microsoft Dynamics 365 Commerce för säkra anrop till API:er ("application programming interfaces"; programmeringsgränssnitt för program) för värderingar och granskningar.

Dynamics 365 Commerce erbjuder [klassificeringar och recensioner](ratings-reviews-overview.md) som en flerkanalslösning. Med den här lösningen kan du komma åt service-API:er från utanför Commerce så att olika uppgifter kan utföras. Uppgifterna inkluderar import av värderingar och granskningar från ditt externa system till Commerce, samt export av värderingar och granskningar från Commerce. Om du vill låta Commerce anropa tjänste-API:er för värdering och granskning på ett säkert sätt måste du först konfigurera S2S-autentisering genom att slutföra procedurerna i denna artikel.

## <a name="add-a-new-app-registration"></a>Lägga till en ny appregistrering

Innan du lägger till en ny appregistrering måste du skapa ett program med hjälp av [Azure-portal](https://portal.azure.com). Om du vill registrera en app i Azure Active Directory (Azure AD) och aktivera autentisering följer du stegen i [Använd Azure Active Directory med en anpassad anslutningsapp Power Automate](/connectors/custom-connectors/azure-active-directory-authentication).

Samla in följande ID från Azure-portal. Du behöver dessa ID:n i stegen som följer.

- Klientprogram-ID
- Klientkatalog-ID (innehavare)

För att lägga till ny appregistrering till en sida i Commerce webbplatsskaparen.

1. Gå till **Start \> Recensioner \> Inställningar**.
1. Under **S2S-autentisering (Service-to-Service)**, välj **Hantera**.

    ![Hantera knappen i avsnittet Service-to-Service (S2S) autentisering i Commerce webbplatsskaparen.](media/Ratings-reviews-settings-service-to-service-authentication.png)

1. I rutan **S2S apposter** som visas till höger, välj **Lägg till en ny S2S appregistrering**.
1. I dialogrutan **Lägg till S2S appost** anger du följande nödvändiga information. Använd värdena från din Azure-programregistrering.

    - **Namn** – Ange namnet på din app (t.ex. **Fabrikama-pp**).
    - **Klient app-ID** – Ange app-ID (till exempel **00000000-0000-0000-0000-000000000000**).
    - **Katalog-ID (innehavare)** – Ange katalog-ID (till exempel **00000000-0000-0000-0000-000000000000**).

    ![Dialogrutan Lägg till S2S appost i Commerce-webbplatsbyggaren.](media/Ratings-reviews-settings-S2S-APP-entry.png)

1. Välj **skicka**. Namnet på din app ska visas i listan på sidan **S2S apposter**.
1. Stäng fönstret **S2S apposter**.
1. Välj **Spara**.

## <a name="edit-an-existing-app-registration"></a>Redigera en befintlig appregistrering

För att redigera en befintlig appregistrering till en sida i Commerce webbplatsskaparen.

1. Gå till **Start \> Recensioner \> Inställningar**.
1. Under **S2S-autentisering (Service-to-Service)**, välj **Hantera**.
1. I fönstret **S2S-apposter** väljer du symbolen symbol bredvid posten som du vill redigera.
1. Uppdatera värdena i fälten **Namn**, **Klientapp-ID** och **Katalog-ID (innehavare)** efter behov.
1. Välj **skicka**.
1. Stäng fönstret **S2S apposter**.
1. Välj **Spara**.

## <a name="remove-an-existing-app-registration"></a>Ta bort en befintlig appregistrering

För att ta bort en befintlig appregistrering till en sida i Commerce webbplatsskaparen.

1. Gå till **Start \> Recensioner \> Inställningar**.
1. Under **S2S-autentisering (Service-to-Service)**, välj **Hantera**.
1. I fönstret **S2S-apposter** väljer du symbolen papperskorgsymbolen bredvid posten som du vill ta bort. Posten tas bort från listan.
1. Stäng fönstret **S2S apposter**.
1. Välj **Spara**.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](ratings-reviews-overview.md)

[Välj att använda omdömen och recensioner](opt-in-ratings-reviews.md)

[Hantera omdömen och recensioner](manage-reviews.md)

[Konfigurera omdömen och recensioner](configure-ratings-reviews.md)

[Synkronisera produktklassificeringar](sync-product-ratings.md)

[Aktivera manuell publicering av omdömen och recensioner genom en moderator](manual-publish-rating-reviews.md)

[Importera och exportera värderingar och granskningar](import-export-reviews.md)

[Vanliga frågor och svar om omdömen och recensioner](ratings-reviews-faq.md) 
