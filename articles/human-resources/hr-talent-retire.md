---
title: Avyttring Dynamics 365 Talent - Registrera och registrera program
description: Det här ämnet beskriver utrangering av Dynamics 365 Talent - Attract- och Onboard-appar.
author: twheeloc
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 3039b0a837335a777cdd6ff22b8b6e7c014ef956
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845096"
---
# <a name="dynamics-365-talent-attract-and-onboard-apps-retirement"></a>Dynamics 365 Talent: Attract och utrangering av Onboard-appar


I december 2019 meddelade vi att vi den 1 februari 2022 sker utrangering av Dynamics 365 Talent - Attract- och Onboard-appar och ge våra kunder två år att planera.

Mer information om hur utrangerar dessa program finns i:
 - [Ta Dynamics 365 Talent och Attract- och Dynamics 365 Talent: Onboard-appar ur bruk](https://community.dynamics.com/365/humanresources/b/dynamics365forhumanresources/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
 - [Skapa en mer lyckad personal med Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources)

Vi fortsätter att stödja Dynamics 365 Human Resources som kommer att hjälpa kunderna att få insikter i personalen som behövs för att bygga databaserade medarbetarerfarenheter inom flera olika områden, till exempel:

- Kompensation
- Förmåner
- Tjänstledighet och frånvaro
- Regelefterlevnad
- Payroll
- Feedback för prestation
- Utbildning och certifiering
- Självbetjäningsprogram

## <a name="dynamics-365-talent-apps-retirement-faq"></a>Vanliga frågor om utrangering av Dynamics 365 Talent

### <a name="what-is-the-user-experience-for-both-dynamics-365-talent---attract-and-onboard-apps-starting-february-1-2022"></a>Vad är användarens erfarenhet för både Dynamics 365 Talent - Attract- och Onboard-appar med början den 1 februari 2022?

Användarna kan inte använda programmen och de omdirigeras till en utrangeringssida.

### <a name="can-customers-continue-to-export-data-for-both-dynamics-365-talent---attract-and-onboard-apps-after-february-1-2022"></a>Kan kunder fortsätta att exportera data för både Dynamics 365 Talent - Attract- och Onboard-appar efter den 1 februari 2022?
  
Nej, utrangering meddelades i december 2019 och den nödvändiga exportkapaciteten angavs till 1 februari 2022. 

### <a name="will-the-customers-data-related-to-both-dynamics-365-talent---attract-and-onboard-apps-in-dataverse-be-deleted-after-february-1-2022"></a>Kommer kundens data som är relaterade till båda Dynamics 365 Talent - Attract- och Onboard-apparna i Dataverse att raderas efter 1 februari 2022?

Nej, entiteterna Dataverse kvarstår i kundens Microsoft Dataverse miljö även efter pensioneringen om inte lösningen Human Capital Management Talent tas bort eller avinstalleras.

### <a name="i-know-the-name-of-the-talent-environment-how-can-i-see-the-attract-and-onboard-data-in-dataverse"></a>Jag känner till namnet på Talent-miljön. Hur kan jag se Attract- och Onboard-data i Dataverse?

1.  Logga in på Power Apps: https://make.powerapps.com
2.  Välj den miljö där du vill se Attract och Onboard-data.
3.  Gå till **Dataverse > Tabeller**. 
4.  Skriv "msdyn_" i **sökning**. Om du ser listan med tabeller som börjar med "msdyn_" + tabellnamn (exempel: msdyn_candidate) så har du hittat miljön med Attract- och Onboard-data.

[![Power Apps](./media/Powerapps.png)](./media/Powerapps.png)

### <a name="i-dont-know-the-name-of-the-talent-environment-how-can-i-find-the-environment-that-has-the-data-for-the-dynamics-365-talent-attract-and-dynamics-365-talent-onboard-applications"></a>Jag känner inte till namnet på Talent-miljön. Hur kan jag hitta miljön som innehåller data för Dynamics 365 Talent: Attract och Dynamics 365 Talent: Onboard-appar?

1)  Logga in på Power Platform administrationscenter: https://admin.powerplatform.microsoft.com/
2)  Välj **Miljö**.
3)  Välj en viss miljö att utvärdera.
4)  Välj **Resurser > Dynamics 365-appar**.
5)  Om du ser lösningen **HCM Talent** installerad, bör den här miljön ha Attract- och Onboard-data lagrade i sig. 

[![Power Platform](./media/HCMTalent.png)](./media/HCMTalent.png)

> [!NOTE] 
> Lösningen **HCM Talent** används också i Dynamics 365 Human Resources.
