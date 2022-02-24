---
title: Nyheter och ändringar i Dynamics 365 Talent (16 juli 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: cd7f288e5c1015f4266db527adfcd62a5dbbc95f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528111"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-16-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (16 juli 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Kommer snart i Attract
#### <a name="job-approvals-appear-on-the-home-page"></a>Jobbgodkännanden visas på startsidan

Godkännanden visas i avsnittet **Godkännanden** på instrumentpanelen. Godkännare kan granska godkännanden under **tilldelade dig**, som visar jobb-ID, jobbtitel, andra godkännare och datum när jobbet tilldelades. Användare som skickar ett jobb för godkännande kan granska sina jobb under **Begärdaav dig** vilket visar de godkännare som fortfarande måste godkänna det överförda jobbet.

## <a name="changes-in-onboard"></a>Ändringar i Onboard
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR
Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2390.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Common Data Service-entiteter som nu stöder anpassade fält

- BusinessProcessCalendar                     
- BusinessProcessGroupAssignment         
- BusinessProcessStage                          
- BusinessProcessTemplateHeader          
- BusinessProcessTemplateTask            
- HcmBenefitOption                              
- HcmBenefitType                                  
- HcmCompensationGrid                            
- HcmCompensationLevel                          
- HcmCompensationPayFrequency                 
- HcmCompensationReferencePointSetup        
- HcmCompensationReferencePointSetupLine 
- HcmCompensationRegion                     
- HcmCompFixedPlanTable                     
- HcmEmployment                                
- HcmEthnicOrigin                                
- HcmFixedCompensationEvent                 
- HcmJob                                           
- HcmJobFunction
- HcmJobType
- HcmLanguageCode
- HcmPayrollCalculationFrequency
- HcmPosition
- HcmPositionType
- HcmSkillType
- HcmVeteranStatus
- HcmWorkCalendarHoliday
- HcmWorkCalendarHolidayLine
- HcmWorker
- HcmWorkerPersonalDetail
- LeaveType
- OMDepartment
- OMLegalEntity
- PayCycle
- PayPeriod
- PayrollBenefitCalculationRate
- PayrollBenefitCalculationRateDetail
- PayrollEarningCode

### <a name="unable-to-see-goals-and-reviews-in-manager-self-service"></a>Det går inte att se mål och granskningar i självbetjäning för chefer

Denna veckas ändringar tillåter nu att du visar och redigerar mål och granskningar för chefer på överhoppningsnivå i självbetjäning för chefer.

### <a name="goal-form-cannot-be-closed-after-a-user-edits-any-goal-field"></a>Det går inte att stänga målformuläret efter att en användare har redigerat ett målfält

I den här versionen åtgärdas ett problem där målformuläret inte stängs när **stängning** väljs.

### <a name="creating-new-goals-and-saving-displays-error"></a>Skapa nya mål och spara visar fel

Den här versionen åtgärdar ett problem när de sparar mål i självbetjäning för medarbetare och chef.

### <a name="unable-to-add-a-field-to-position-details"></a>Det går inte att lägga till ett fält till befattningsdetaljer 

I den här versionen stöds nu anpassade fält i befattningsdetaljer.
 
### <a name="unable-to-set-up-expiring-date-on-the-earning-code-through-data-management"></a>Det går inte att ställa in förfallodatum för den aktuella koden via datahantering

Nu kan du med ändringarna ange utgångsdatum för hanteringen av koder i datahanteringen.

### <a name="new-custom-fields-dont-sync-quickly-enough"></a>Nya anpassade fält synkroniseras inte tillräckligt snabbt

Prestanda för synkronisering av anpassat fält till Common Data Service har förbättrats med den här veckans version.

### <a name="entity-export-to-database-jobs-fail-with-error-message-format-of-the-initialization-string-does-not-conform-to-specification-starting-at-index-0"></a>Entitetexport till databasjobb misslyckas med felmeddelandet: "formatet på initieringssträngen följer inte specifikationen med början på index 0."

Den här versionen korrigerar problemet där det inte går att köra batchjobb för databas. Att uppdatera manuellt:

1. Gå till **Datahantering**.
2. Välj **Konfigurera enhetsexport till databas**.
3. Ange anslutningssträngen igen till måldatabasen och välj **Spara**.

### <a name="smtp-email-configuration-suddenly-fails-with-error-message-the-smtp-server-requires-a-secure-connection-or-the-client-was-not-authenticated"></a>SMTP-e-postkonfiguration misslyckas plötsligt med felmeddelandet: "SMTP-servern kräver en säker anslutning eller så har klienten inte autentiserats."

Den här versionen korrigerar en SMTP-e-postkonfiguration som plötsligt misslyckas. Att uppdatera manuellt:

1. Gå till **Systemadministration**.
2. Välj **E-postparametrar**.
3. Välj **SMTP-inställningar**. 
4. Ange det användarnamn och lösenord som ska användas på SMTP-servern igen och välj **Spara**.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Förhandsgranskningsfunktioner aktiveras endast i begränsade instanser

När du etablerar en ny instans av Talent kan du ange om instanstypen är **produktion** eller **begränsat läge**. Med instanser **Begränsat läge** kan tidig test av nya funktioner göras. Alla befintliga Talent-instanser kommer att uppdateras till instanstypen **produktion**. Om du vill uppdatera en av dina befintliga förekomster till instanstypen **Begränsat läge** kontaktar du [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) för att initiera ändringsbegäran.

Mer information om hur du ändringar publiceras finns i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Begränsa tjänstledighetstyperna i ledighetsansökningar

Organisationer kan erbjuda många olika typer av tjänstledighet till medarbetarna. Det är dock inte lämpligt att låta medarbetarna skicka ut ledighetsbegäranden för vissa tjänstledighetstyper. Dessa tjänstledighets typer kan hanteras av personal i stället. Med den här versionen kan du konfigurera vilka tjänstledighetstyper som medarbetare kan skicka ut ledighetsansökningar för. 

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Visa prestandainformation för direkta och utökade rapporter i Självbetjäning för chefer

Med ett nytt alternativ kan cheferna visa prestandan för både deras direktrapporter och de utökade rapporterna. För närvarande kan linjechefer tilldela och uppdatera resultatmål och utfärda nya recensioner. Dessutom kan direktchefer och deras medarbetare underhålla och uppdatera prestandajournaler för att säkerställa att processen för resultatöversynen går smidigt. När den här ändringen har implementerats kan chefer visa och underhålla prestandarelaterad information för sina utökade rapporter utöver deras underställda.
