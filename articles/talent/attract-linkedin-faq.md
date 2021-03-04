---
title: Vanliga frågor om LinkedIn-integration
description: I det här ämnet besvaras frågor som du kan ha om integrering mellan LinkedIn och Microsoft Dynamics 365 Talent - Attract.
author: hasrivas
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 35428da709f480e1d3842b7e92deacba200326ee
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462559"
---
# <a name="linkedin-integration-faq"></a>Vanliga frågor om LinkedIn-integration

[!include [banner](includes/banner.md)]

LinkedIn är världens största professionella nätverk online. Microsoft Dynamics Talent: Attract integreras med LinkedIn för att ge dig tillgång till världens främsta talanger. Attract låter dig publicera jobb direkt på LinkedIn och du kan också dra information om kandidater från LinkedIn till Attract.

## <a name="for-recruiters-and-hiring-managers"></a>För rekryterare och personalchefer

Här följer svar på vanliga frågor om hur man använder Attract och LinkedIn.

### <a name="what-linkedin-features-do-i-get-with-attract"></a>Vilka LinkedIn-funktioner får jag med Attract?

Attract-integration med LinkedIn gör att du kan utföra följande uppgifter:

- [Publicera jobb till LinkedIn](./attract-post-jobs-to-linkedin.md) (som begränsade listor).
- [Skaffa kandidater med LinkedIn Recruiter i Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md#export-linkedin-candidates-to-attract-with-one-click)
- [Konfigurera integration med LinkedIn för Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md#set-up-apply-with-linkedin-in-attract).

### <a name="what-do-i-need-before-i-can-post-jobs-to-linkedin"></a>Vad behöver jag för att kunna publicera jobb på LinkedIn?

Din administratör måste [konfigurera LinkedIn-integration i Attract](./attract-admin-linkedin.md#configure-job-posting-to-linkedin). Sedan kan du sätta igång.

### <a name="how-do-i-post-jobs-to-linkedin-from-attract"></a>Hur publicerar jag jobb på LinkedIn från Attract?

När du har skapat ett jobb i Attract måste du bara markera knappen **skicka nu** som motsvarar LinkedIn. Mer information finns i [Publicera jobb till LinkedIn från Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md#post-jobs-to-linkedin).

### <a name="can-i-get-candidate-information-from-linkedin-into-attract"></a>Kan jag få information om kandidat från LinkedIn i Attract?

Ja. Om du ser en bra kandidat på LinkedIn kan du enkelt exportera kandidatens information till Attract. Mer information finns i [Hitta kandidater med LinkedIn Recruiter i Microsoft Dynamics 365 Talent - Attract](attract-linkedin-recruiter.md).

### <a name="how-can-i-get-help-accessing-linkedin-from-attract"></a>Hur får jag hjälp med åtkomst till LinkedIn från Attract?

Om du har problem med att logga in eller publicera jobb på LinkedIn från Attract, se [Felsök integration med LinkedIn och Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md).

För andra problem med Attract, se [Få stöd för Microsoft Dynamics 365 Talent](./talent-support.md). Mer information om LinkedIn finns på [LinkedIn supportsidan](https://www.linkedin.com/help).

## <a name="for-admins-and-developers"></a>För administratörer och utvecklare

Här följer svar på vanliga frågor om hur man konfigurerar integration mellan Attract och LinkedIn.

### <a name="how-do-i-configure-attract-so-that-recruiters-and-hiring-managers-can-post-jobs-to-linkedin"></a>Hur konfigurerar jag Attract så att rekryterings- och anställningsansvariga kan publicera jobb till LinkedIn?

Du kan konfigurera de tillgängliga alternativen på fliken **LinkedIn-integration** i Administrationscenter. Mer information finns i [ställa in integration med LinkedIn för Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md).

### <a name="can-i-export-candidate-information-from-linkedin"></a>Kan jag exportera information om kandidater från LinkedIn?

Ja, men du måste först konfigurera integrationen med LinkedIn Recruiter. Mer information finns i [ställa in integration med LinkedIn för Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md).

### <a name="how-can-i-post-jobs-to-premium-job-slots-on-linkedin"></a>Hur gör jag för att publicera jobb på Premium jobbplatser på LinkedIn?

Även om Attract har en kraftfull lösning för publicering av jobb till LinkedIn, kanske du behöver ytterligare flexibilitet. Du kanske till exempel vill kunna publicera Premium jobbplatser utöver de begränsade listorna, eller så kanske du vill att LinkedIn ska bearbeta publiceringar i batchjobb mer än en gång per dag.

#### <a name="types-of-linkedin-job-posts"></a>Typer av LinkedIn-jobbpubliceringar

LinkedIn erbjuder följande typer av jobbpubliceringar

- **Begränsad lista** – gratis jobbpubliceringar som visas i sökresultat när kandidater söker efter jobb på LinkedIn och på ett företags LinkedIn-sida. Begränsade listor är riktade mot aktiva jobbsökande. Den här typen av lista är den typ som Attract ger LinkedIn. Du kan inte marknadsföra begränsade listor-jobb på LinkedIn. Om du vill marknadsföra begränsade listor måste du arbeta med LinkedIn för att kunna aktivera Jobbförpackning. Mer information om Jobbförpackning finns i [Begränsade listor jämfört med Premium jobbplatser för jobbförpackning](https://www.linkedin.com/help/recruiter/answer/79049/limited-listings-vs-premium-job-slots-for-job-wrapping) och [jobbförpackning plus - vanliga frågor](https://www.linkedin.com/help/recruiter/answer/79050/job-wrapping-frequently-asked-questions).
- **Premium jobbplatser** – inköpta publiceringar som visas på olika platser på LinkedIn, t.ex. LinkedIn-feed, e-postmeddelanden och området **Jobb du kanske är intresserad av**. Premium jobbplatser är riktade mot passiva kandidater, men de visas också vid jobbsökning.

Attract publicerar jobb till LinkedIn som som begränsade listor. Om du vill använda Premium jobbplatser måste du använda jobbförpackning via LinkedIn Recruiter. Jobbförpackning kräver ett jobbförpackningsavtal med LinkedIn. Mer information finns i [Jobbförpackning via LinkedIn Recruiter - Översikt](https://www.linkedin.com/help/recruiter/answer/79037).

#### <a name="frequency-of-batch-processing-on-linkedin"></a>Frekvens för batchbearbetning på LinkedIn

LinkedIn behandlar jobbpubliceringar i en batch via Attract en gång per dag. Därför kan det ta upp till 48 timmar innan jobb visas på LinkedIn efter att de har publicerats via Attract. Om du vill att jobb ska visas snabbare på LinkedIn, eller om du behöver någon ytterligare flexibilitet, kan du använda API (application programming interface) för Recruiter System Connect från LinkedIn. Mer information finns i [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect).

#### <a name="table-of-options-for-job-posting-to-linkedin"></a>Register över alternativ för jobbpublicering till LinkedIn

I följande tabell beskrivs de olika alternativen för publicering av jobb till LinkedIn. Det inkluderar fördelarna med varje alternativ och ytterligare information.

|  | Attract | Jobbförpackning genom LinkedIn Recruiter | Recruiter System Connect API |
|---|---|---|---|
| **Beskrivning** | Attract publicerar jobb till LinkedIn som en XML-feed. | Företagets kontrakt med LinkedIn och innehåller ett XML-flöde för publicering av jobb. | Kunden använder API för att synkronisera information mellan Attract och LinkedIn Recruiter. |
| **Vilken typ av jobb kan jag publicera?** | Begränsad lista | Premium jobbplats eller Begränsad lista | Begränsad lista |
| **Kan jag marknadsföra jobbet på LinkedIn?** | Nej | Premium jobbplatser: Ja<br>Begränsade listor: Nej | Nej |
| **Hur ofta publiceras LinkedIn-jobb?** | En gång per dag | En gång per dag | Flera gånger per dag, enligt vad som definieras av API:n |
| **Rekommenderas av LinkedIn?** | Nej | Ja | Nej |
| **Vad ska jag göra?** | Köpa Attract | Ett jobbförpackningsavtal med LinkedIn och köpa Premium jobbplatser | Ett API-avtal med LinkedIn | 
| **Var hittar jag mer information?** | [Konfigurera integration med LinkedIn för Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md) | [Jobbförpackning genom LinkedIn Recruiter - Översikt](https://www.linkedin.com/help/recruiter/answer/79037) | [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect) |

> [!NOTE]
> Du behöver ingen LinkedIn Recruiter System Connect-licens för att publicera jobb på LinkedIn med Attract.

## <a name="see-also"></a>Se även

[Konfigurera integration med LinkedIn för Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md)

[Publicera jobb på LinkedIn från Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md)

[Skaffa kandidater med LinkedIn Recruiter i Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md)

[Felsöka integrering med LinkedIn och Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]