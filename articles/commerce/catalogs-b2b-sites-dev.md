---
title: Utbyggbarhetspåverkan av Commerce-kataloger för B2B-anpassningar
description: Denna artikel beskriver utvidgningar av Commerce-katalogerna för B2B-funktionen i Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: a9abdb5ea702917a745c3156f774aade757c159e
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027264"
---
# <a name="extensibility-impact-of-commerce-catalogs-for-b2b-customizations"></a>Utbyggbarhetspåverkan av Commerce-kataloger för B2B-anpassningar

[!include [banner](includes/banner.md)]

Denna artikel beskriver utvidgningseffekten av funktionen **Commerce-kataloger för B2B** i Microsoft Dynamics 365 Commerce.

Om du är intresserad av att utöka katalogkontexten till anpassade scenarier måste du kanske uppdatera dina anpassningar. Uppdateringen följer den standardprocess som kunderna måste ha efter sig, eftersom deras anpassningar eventuellt inte har automatiskt stöd för de senaste funktionerna efter att uppgraderingen är klar. Om det finns någon ny funktion eller korrigeringsalternativ för dina anpassningar i dina erfarenheter rekommenderar vi att du uppdaterar anpassningskoden efter detta. Denna uppdatering liknar de ändringar som Microsoft kan ha gjort för kärnkoden.

Gå igenom anpassningsfallen som följer och ta reda på om dina anpassningar måste uppdateras.

> [!NOTE]
> - Alla marknadsföringsgränssnitt (API:er) ska vara katalogmeddelade. Därför är det mycket viktigt att du passerar parametern **CatalogID**.
> - Standardkatalogen (**CatalogID**=**0**) ett giltigt katalog för signerade B2B-användare (business-to-business). Därför misslyckas alla API-anrop som passerar "0" eller använder ett standardvärde, eftersom siteanvändare inte har åtkomst till katalog 0. För att få rätt erfarenhet måste kund-API-anropen uppdateras så att de passerar katalog-ID:t som valts i katalogväljaren. Om du använder ett standardvärde och användaren byter katalog bör webbplatsen ange data för den valda katalogen. Därför bör anpassade API:er för att matcha de API:er som körs från kärnhandelskoden skicka den valda katalogen.

Följande anpassningsalternativ kräver utvecklingsuppdateringar:

- **Ärende 1:** En kund introducerar sin egen [dataåtgärd](e-commerce-extensibility/data-actions.md) som anropar en produktrelaterad API eller dataåtgärd. Följande uppdateringssteg är nödvändiga:

    1. Om dataåtgärden använder ett direkt API-anrop uppdaterar du dataåtgärden så att den passerar katalog-ID:t, vilket visas i illustrationen nedan.

        ![Uppdaterad dataåtgärd som passerar katalog-ID:t.](./media/customization1_a.png)

    1. Om dataåtgärden anropar en annan produktrelaterad dataåtgärd i anpassningen måste koden uppdateras så att den passerar några nya parametrar, till exempel **requestContext** . Parametern **requestContext** används för att hämta det aktuella katalog-ID:t, på det sätt som visas i följande exempelillustratör.

        ![Uppdaterad dataåtgärd som passerar den nya parametern.](./media/customization1_b.png)

- **Ärende 2:** En kund har en [åsidosätta dataåtgärd](e-commerce-extensibility/data-action-overrides.md). Följande uppdateringssteg är nödvändiga:

    - Uppdatera dataåtgärden i ärende 1.

- **Ärende 3:** En kund har ett visningstillägg, skriptinmatarmodul eller [klonad modul](e-commerce-extensibility/modules-overview.md#clone-a-module-library-module) som innehåller samtal till API:er eller dataåtgärder. Följande uppdateringssteg är nödvändiga:

    - Uppdatera koden som för ärende 1, på det sätt som visas i följande exempel illustration.

       ![Uppdaterad kod som passerar den nya parametern.](./media/customization3.png)

- **Ärende 4:** En kund använder ett **getById**-API-samtal. Följande uppdateringssteg är nödvändiga:

    - Växla till **getByIds** API-anropet istället eftersom **getById** APT-anropet har vissa begränsningar och inte stöder katalogmeddelar.

- **Ärende 5:** En kund har en dataåtgärd som hämtar information för flera produkter som kan finnas i olika kataloger. Följande uppdateringssteg är nödvändiga:

    - Dela API-anropen per katalog-ID. För kundvagns-API:er kan vagnen till exempel innehålla produkter från olika kataloger. Produktraderna bör grupperas efter katalog-ID och de ska anropa API:t för varje katalog separat, vilket visas i följande exempel illustratör.

        ![Uppdaterad dataåtgärd som grupperar produktrader efter katalog-ID.](./media/customization5.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa handelskataloger för B2B-webbplatser](catalogs-b2b-sites.md)

[Vanliga frågor om handelskataloger för B2B](catalogs-b2b-sites-FAQ.md)
