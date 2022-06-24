---
title: Fördröjning av exakt pris- och rabattberäkning för förbättrad prestanda
description: Denna artikel beskriver den beräkningskapacitet för försenat pris som är tillgänglig i kassa (POS) och kundtjänst för Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 09/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 6926c288a91dbe66b6ffc2e6c06f866d3ebd7652
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845907"
---
# <a name="delay-exact-price-and-discount-calculation-for-improved-performance"></a>Fördröjning av exakt pris- och rabattberäkning för förbättrad prestanda

[!include [banner](includes/banner.md)]

Denna artikel beskriver den beräkningskapacitet för försenat pris som är tillgänglig i kassa (POS) och kundtjänst för Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce har stöd för generering av samköpsrabatter som tillämpas när flera försäljningsrader i en försäljningsorder eller försäljningsoffert kombineras. Rabatterna kan till exempel vara mixa och matcha, tröskel- och kvantitetsrabatter.

När en ny rad läggs till i en order, utvärderar Commerce-prismotorn hela vagnen för att avgöra om någon av dessa samköpsrabatter kan användas. På grund av omberäkningen kan tillägg av nya rader påverka resultatet när en försäljningsorder växer.

B2B-företag (Business-to-Business) och vissa B2C-företag (business-to-consumer) har dock ofta stora orderstorlekar. Därför kan det ta lång tid att vänta tills prissättningsmotorn räknas om efter att varje artikel har lagts till i vagnen. För stora order är det dessutom vanligtvis inte särskilt viktigt att det exakta priset och rabatten visas varje gång en artikel läggs till i vagnen. Det är viktigt att användarna snabbt kan lägga till artiklar. Möjligheten att försena en exakt pris- och rabattberäkning tills en användare begär det eller en order har slutföras kan förbättra prestandan avsevärt. Det kan också minska den tid som går åt för att slutföra beställningen.

Möjligheten att försena exakt pris- och rabattberäkning har länge varit tillgänglig i kassa. Från och med versionen Commerce version 10.0.22 är den även tillgänglig för kundtjänst.

## <a name="enable-delayed-price-and-discount-calculation-for-pos"></a>Aktivera fördröjningsberäkning av pris och rabatt för kassa

För att aktivera fördröjningsberäkning av pris och rabatt för kassa, följ dessa steg.

1. I Commerce headquarters går du till funktionalitetsprofilen som är kopplad till den fysiska butiken.
1. På snabbfliken **Belopp** aktiverar du konfigurationen **Manuell beräkning av flera artikelrabatter**.
1. Öppna layoutdesignern för skärmen för de kassor där den försenade beräkningen ska aktiveras.
1. Lägg till en knapp för åtgärden **Beräkna summa** till önskad knappsats.
1. Kör jobben **1070** och **1090**.

När artiklar läggs till i en transaktion beräknas inte samköpsrabatter om kassören inte väljer knappen **Beräkna summa**. När **Beräkna total** väljs för en transaktion, beräknas alltid samköpsrabatter för den. Kassören behöver inte välja knappen igen, även om ytterligare artiklar läggs till i vagnen. Systemet tillåter inte att kassören fångar in betalningar förrän **Beräkna summa** har valts.

## <a name="enable-delayed-price-and-discount-calculation-for-call-center"></a>Aktivera fördröjningsberäkning av pris och rabatt för kundtjänst

För att aktivera fördröjningsberäkning av pris och rabatt för kundtjänst, följ dessa steg.

1. I Commerce headquarters, gå till **Arbetsytan \> Funktionshantering**.
1. Aktivera funktionen **Förhindra oavsiktlig prisberäkning för handelsorder**. Den här funktionen är en förutsättning för att det ska gå att beräkna det fördröjt pris och rabatt.

    > [!NOTE]
    > För nya distributioner är funktionen **Förhindra oavsiktlig prisberäkning för handelsorder** aktiverad som standard.

1. Gå till **Commerce-paramtrar \> Priser och rabatter**.
1. I avsnittet **Övriga avgifter**, aktivera konfigurera **Beräkna priser på flera rader och rabatter manuellt**.

När en försäljningsorder eller försäljningsoffert skapas eller redigeras i kundtjänst, försenas den exakta pris- och rabattberäkningen för den. Prissättningsmotorn tar bara hänsyn till den försäljningsrad som läggs till eller redigeras, och ignorerar alla andra försäljningsrader. Nettobeloppet för en artikel inkluderar prisberäkningen och enkla rabatter (rabattprocent eller rabattbelopp för en enskild artikel). Mixa och matcha, tröskel- och kvantitetsrabatter används inte. Kundtjänstanvändare som vill visa det exakta priset, inklusive alla rabatter, kan välja en av de tre knapparna: **Omberäkna**, **Summor** eller **Komplett**.

> [!NOTE]
> För kundtjänstorder visar systemet ett varningsmeddelande för att påminna användaren om att de måste välja knappen **Omberäkna**, **Summor**, eller **Slutför** för att göra exakt pris och rabattberäkning. För order där knappen **Slutför** är tillgänglig, finns det inget sätt för kundtjänstanvändaren att utelämna den exakta pris- och rabattberäkningen, eftersom de måste välja **Slutför** för att slutföra beställningen. För order där knappen **Slutför** inte är tillgänglig, finns det ingen åtgärd som indikerar att beställningen har slutförts. Därför ansvarar kundtjänstanvändaren för att välja antingen **Omberäkna** eller **Summor** innan de slutför orderinregistreringen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
