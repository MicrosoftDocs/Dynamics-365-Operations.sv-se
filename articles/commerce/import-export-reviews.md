---
title: Importera och exportera värderingar och granskningar
description: I denna artikel beskrivs hur du importerar och exporterar produktklassificeringar och -granskningar i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: f369e3cd208cdfba816f817ead75374ee6982912
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271946"
---
# <a name="import-and-export-ratings-and-reviews"></a>Importera och exportera värderingar och granskningar

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du importerar och exporterar produktklassificeringar och -granskningar i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce erbjuder [klassificeringar och recensioner](ratings-reviews-overview.md) som en flerkanalslösning. När du växlar till lösningen för värderingar och granskningar i Dynamics 365 Commerce kan du flytta dina befintliga värderingar och granska data över till Commerce plattform. Du kanske också vill exportera värderingar och data från Commerce, utifrån dina affärsbehov. Med hjälp av Power Automate anslutningsapp kan du importera omdömen och recensioner till Commerce och exportera dem från Commerce.

> [!NOTE]
> Information om hur du kommer igång med logikflöden finns Power Automate i [Skapa ett molnbaserade flöde i Power Automate](/power-automate/get-started-logic-flow).

## <a name="prerequisites"></a>Förutsättningar

Innan du kan importera och exportera värderingar och granskningar måste du uppfylla följande förutsättningar:

- Lösningen för omdömen och recensioner måste vara aktiverad för din näthandelsplats på Commerce-plattformen. Mer information finns i [Välj att använda omdömen och recensioner](opt-in-ratings-reviews.md).
- Dynamics 365 omdömen och recensioner Power App anslutningsapp måste konfigureras för att aktivera åtgärder som "skicka granskningar" eller "exportgranskningar" i Power Automate. Mer information finns i [Dynamics 365 Commerce - omdömen och recensioner (förhandsversion)](/connectors/dynamics365ratingsre/).
- Service-to-Service (S2S)-autentisering måste konfigureras för att på ett säkert sätt anropa klassificeringar och recensioner Application Programming Interface (API) utanför Commerce. Mer information finns i [Konfigurera Service-to-Service-autentisering](service-to-service-auth.md).

## <a name="import-ratings-and-reviews"></a>Importera omdömen och recensioner

Om du vill importera värderingar och data från ditt befintliga system till Commerce måste du lägga till Dynamics 365 omdömen och recensioner Power Automate anslutningsapp till antingen ett befintligt Power Automate flöde eller ett nytt. Mer information finns i [Dynamics 365 Commerce - omdömen och recensioner (förhandsversion)](/connectors/dynamics365ratingsre/).

> [!IMPORTANT]
> Innan du kan slutföra denna procedur måste du [konfigurera S2S autentisering](service-to-service-auth.md).

Om du vill importera omdömen och recensioner till Commerce genom att använda Dynamics 365 omdömen och recensioner Power Automate anslutningsappen följer du dessa steg.

1. Välj åtgärden **Skicka in användarrecension**.
1. Upprätta en anslutning genom att använda Azure Active Directory (Azure AD) appinformation som skapades när du konfigurerade S2S-autentisering. Mer information finns i [Konfigurera Service-to-Service-autentisering](service-to-service-auth.md).
1. Åtgärden **Skicka användargranskning** gör en granskning åt gången. Upprepa därför åtgärden. Använd källgranskningarna som en lista när du skickar bulkgranskningar.
    
## <a name="export-ratings-and-reviews"></a>Exportera omdömen och recensioner

Om du vill exportera värderingar och data från Commerce måste du lägga till Dynamics 365 omdömen och recensioner Power Automate anslutningsapp till antingen ett befintligt Power Automate flöde eller ett nytt. Mer information finns i [Dynamics 365 Commerce - omdömen och recensioner (förhandsversion)](/connectors/dynamics365ratingsre/).

Om du vill exportera omdömen och recensioner från Commerce genom att använda Dynamics 365 omdömen och recensioner Power Automate anslutningsappen följer du dessa steg.

1. Välj åtgärden **Exportera alla omdömen**.
1. Slutför åtgärden. 

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över omdömen och recensioner](ratings-reviews-overview.md)

[Välj att använda omdömen och recensioner](opt-in-ratings-reviews.md)

[Hantera omdömen och recensioner](manage-reviews.md)

[Konfigurera omdömen och recensioner](configure-ratings-reviews.md)

[Synkronisera produktklassificeringar](sync-product-ratings.md)

[Aktivera manuell publicering av omdömen och recensioner genom en moderator](manual-publish-rating-reviews.md)

[Konfigurera tjänst-till-tjänst-autentisering](service-to-service-auth.md)

[Vanliga frågor och svar om omdömen och recensioner](ratings-reviews-faq.md)
