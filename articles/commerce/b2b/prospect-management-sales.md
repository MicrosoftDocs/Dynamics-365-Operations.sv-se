---
title: Hantera affärspartnersanvändare på B2B-näthandelssajter som använder Dynamics 365 Sales
description: Det här avsnittet beskriver hur man använder Microsoft Dynamics 365 Sales för att hantera affärspartners godkännande för Dynamics 365 Commerce B2B-webbplatser.
author: shajain
ms.date: 2/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: c6ac5409de5101c91b9348de800e3eaea9895c23
ms.sourcegitcommit: 4d52c67f52ad0add63cd905df61367b344389069
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8312611"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites-using-dynamics-365-sales"></a>Hantera affärspartnersanvändare på B2B-näthandelssajter som använder Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Det här avsnittet beskriver hur man använder Microsoft Dynamics 365 Sales för att hantera affärspartners godkännande för Dynamics 365 Commerce B2B-webbplatser. Organisationer som redan finns i lösningen Dynamics 365 Sales kan använda sina lead- och affärsmöjlighetsbegrepp för en B2B-godkännandeprocess för e-handel.

Bakgrundsinformation om godkännandeprocessen för B2B-affärspartner finns i [Hantera affärspartneranvändare på B2B-e-handelswebbplatser](manage-b2b-users.md).

Potentiella affärspartner kan initiera registreringsprocessen till en B2B-näthandelssajt genom att skicka in registreringsbegäran via en länk på B2B-webbplatsen. När en begäran har skickats och de relevanta jobben (till exempel **P-0001** och **Synkronisera order och kanalbegäranden**) körs i Commerce-administration sparas den aktuella förfrågningen på sidan **Alla potentiella kunder** i Commerce-administration. Processen för godkännande av affärspartners potentiella kund kan sedan slutföras i Sales.

När integrationen mellan Sales och Handel har aktiverats, medför skapandet av en handelspartner i Commerce att en *lead* skapas i Sales.

I följande bild visas ett exempel på en sida för att skapa en lead-sida för en potentiell affärspartner i Sales.

![Sidan Skapa lead i Dynamics 365 Sales.](../media/LeadInSales.png)

I illustrationen visar avsnittet **kontakt** personen som skickade in denna begäran om registrering och avsnittet **Företag** visar organisationen. En notering i avsnittet **Tidslinje** anger att denna lead genererades av infrastruktur för dubbelriktad skrivning. Eftersom den skapades av infrastrukturen för dubbelriktad skrivning, kommer detta lead inte att visas i listrutan **Mina öppna leads**. I stället visas den under en ny vy med namnet **All handel B2B-leads**.

Enligt standardkvalificeringsprocessen för leads i Försäljning, när en användare "kvalificerar" leaden, en post för *affärsmöjlighet* en post för *kontakt* och *konto* skapas. Den infrastruktur för dubbelriktad skrivning som används för att skriva kontakten och kontoposterna till Commerce. Kontakten skapas som kund av typen *person* och företaget skapas som en kund av typen *organisation*. Om en användare väljer **Stäng som vunnen** för affärsmöjligheten, godkänns potentiell kund i Commerce. När en potentiell kund godkänns skapas en kundhierarki.

Alla återstående affärsprocesser förekommer i Commerce. De här processerna inkluderar att skicka e-postmeddelanden till affärspartnern, definiera kreditgränshantering för användarna och lägga till fler användare på B2B-webbplatsen. Om en användare diskvalificerar denna lead eller markerar affärsmöjligheten som förlorad i stället för att kvalificera denna lead, markeras emellertid potentiell kund i Commerce som avvisad och en avböjning via e-post skickas till den som begär det.

## <a name="enable-integration-between-sales-and-commerce"></a>Aktivera integration mellan Sales och Commerce

Integrationen mellan Sales och Commerce bygger på infrastrukturen för dubbelriktad skrivning. Därför ska funktionen dubbelriktad skrivning aktiveras och arbeta så att kunder som skapas i ett system skrivs till det andra systemet. Mer information om infrastruktur för dubbelriktad skrivning finns i översikten [Översikt av dubbelriktad skrivning](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview).

När inställningen av dubbelriktad skrivning har slutförts kan implementeringspartnern gå till [Microsoft AppSource](https://appsource.microsoft.com/) och söka efter lösningen kallad [Commerce-lösningar med dubbelriktad skrivning](https://partner.microsoft.com/dashboard/commercial-marketplace/offers/7ca1d8c9-dc79-4cb7-a82e-8dc96a25acca/overview). Installera paketet med hjälp av standardinstallationsguiden och testa det genom att skapa en potentiell kund på en B2B-webbplats. När potentiell kund har skapats, kontrollera att begäran visas på **alla potentiella kunder** visas i Commerce och kontrollera sedan att potentiell kund visas som en lead i Sales.

## <a name="additional-resources"></a>Ytterligare resurser

[Hantera affärspartnersanvändare på B2B-näthandelssajter](manage-b2b-users.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
