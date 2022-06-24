---
title: Skapa regler för rådgivning om optimering
description: Den här artikeln beskriver hur du lägger till nya regler Optimization advisor.
author: roxanadiaconu
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: sericks
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 1b1d9b14cb67b1dd0a961f6f8618de37147a2c52
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850917"
---
# <a name="create-rules-for-optimization-advisor"></a>Skapa regler för rådgivning om optimering

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur du lägger till nya regler i **Optimization advisor**. Du kan till exempel skapa en ny regel som identifierar vilka anbudsförfrågningar (RFQ) som har en tom rubrik. Att använda titlar på ärenden gör dem lätta att känna igen och sökbara. Även om exemplet är ganska enkelt visar det vad som kan uppnås med optimeringsregler. 

A *regel* är en kontroll av programdata. Om villkoret som regeln beräknar uppfylls skapas möjligheter att optimera processer och förbättra data. Möjligheterna kan utnyttjas och, vid behov, kan inverkan av åtgärderna mätas. 

Så här skapar du en ny regel för **Optimization advisor**. Lägg till en ny klass som utökar den abstrakta klassen **SelfHealingRule** och implementera gränssnittet **IDiagnosticsRule** som dekoreras med attributet **DiagnosticRule**. Klassen måste också ha en metod som dekoreras med attributet **DiagnosticsRuleSubscription**. Enligt praxis görs detta i metoden **opportunityTitle**, som beskrivs senare. Denna nya klass kan läggas till en anpassad modell med ett beroende av modellen **SelfHealingRules**. I följande exempel kallas den regel som implementeras **RFQTitleSelfHealingRule**.

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

Den abstrakta klassen **SelfHealingRule** har metoder som måste implementeras i ärvda klasser. Kärnan är **utvärderingsmetoden** som returnerar en lista över de affärsmöjligheter som har identifierats av regeln. Affärsmöjligheter kan vara per juridisk person eller kan gälla för hela systemet.

```xpp
protected List evaluate() 
{ 
    List results = new List(Types::Record); 
    
    DataArea dataArea; 

    while select id from dataArea 
        where !dataArea.isVirtual 
    { 
        changecompany(dataArea.id) 
        { 
            container result = this.findRFQCasesWithEmptyTitle(); 

            if (conLen(result) > 0) 
            { 
                SelfHealingOpportunity opportunity = this.getOpportunityForCompany(dataArea.Id); 
                opportunity.EvaluationState = SelfHealingEvaluationState::Evaluated; 
                opportunity.Data = result; 
                opportunity.OpportunityDate = DateTimeUtil::utcNow(); 
                
                results.addEnd(opportunity); 
            } 
        } 
    } 
    
    return results; 
} 
```

Metoden ovan loopar över företag och väljer anbudsförfrågningar med tom rubrik i metoden **findRFQCasesWithEmptyTitle**. Om minst ett sådant fall hittas, skapas en företagsspecifik affärsmöjlighet med metoden **getOpportunityForCompany**. Lägg märke till att fältet **Data** i tabellen **SelfHealingOpportunity** är av typen **behållare** och därför kan innehålla all information som berör logiken för regeln. Att ställa in **OpportunityDate** med aktuell tidsstämpel registrerar tidpunkten för den senaste utvärderingen av affärsmöjligheten.  

Affärsmöjligheter kan också vara mellan företag. I detta fall behövs inte loopen över företag och affärsmöjligheten måste skapas med metoden **getOpportunityAcrossCompanies**. 

Följande kod visar metoden **findRFQCasesWithEmptyTitle** som returnerar ID för de anbudsförfrågor som har tomma titlar.

```xpp
private container findRFQCasesWithEmptyTitle() 
{ 
    container result; 

    PurchRFQCaseTable rfqCase; 
    while select RFQCaseId from rfqCase 
        where rfqCase.Name == '' 
    { 
        result += rfqCase.RFQCaseId; 
    } 
    
    return result; 
} 
```

Två ytterligare metoder som måste implementeras är **opportunityTitle** och **opportunityDetails**. Det förra returnerar en kort rubrik för affärsmöjligheten, den senare returnerar en detaljerad beskrivning av affärsmöjligheten, som även kan innehålla data.

Den rubrik som returneras av **opportunityTitle** visas i kolumnen **Optimeringsmöjlighet** i arbetsytan **Optimerings-advisor**. Den visas också som rubrik i det sidofönster som visar mer information om affärsmöjligheten. Enligt praxis dekoreras den här metoden med attributet **DiagnosticRuleSubscription** som har följande argument: 

* **Diagnosområde** – en uppräkning av typen **DiagnosticArea** som beskriver vilket tillämpningsområde regeln tillhör t.ex. **DiagnosticArea::SCM**. 

* **Regelnamn** – en sträng med regelnamn. Namnet visas i kolumnen **Regelnamn** i formuläret **Diagnostikregel – validering** (**DiagnosticsValidationRuleMaintain**). 

* **Körningsfrekvens** – en uppräkning av typen **DiagnosticRunFrequency** som beskriver hur ofta regeln ska köras **DiagnosticRunFrequency::Daily**. 

* **Regelbeskrivning** – en sträng med en mer detaljerad beskrivning av regeln. Namnet visas i kolumnen **Regelbeskrivning** i formuläret **Diagnostikregel – validering** (**DiagnosticsValidationRuleMaintain**). 

> [!NOTE]
> Attributet **DiagnosticRuleSubscription** krävs för att reglerna ska fungera. Det används vanligtvis i **opportunityTitle** men kan dekorera alla metoder i klassen.

Nedan finns ett exempel på implementering. Råa strängar används för enkel hantering, men en korrekt implementering kräver etiketter. 

```xpp
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

Beskrivningen som returneras av **opportunityDetails** visas i det sidofönster som visar mer information om affärsmöjligheten. Detta tar argumentet **SelfHealingOpportunity**, som är fältet **Data** och som kan användas för att ge mer information om affärsmöjligheten. I exemplet returnerar metoden ID på de anbudsförfrågor som har en tom rubrik. 

```xpp
public str opportunityDetails(SelfHealingOpportunity _opportunity) 
{ 
    str details = ''; 
    container opportunityData = _opportunity.Data; 
    int affectedRFQCasesCount = conLen(opportunityData); 

    if (affectedRFQCasesCount != 0) 
    { 
        details = 'The following Request for Quotation cases have an empty title:\n'; 
        for (int i = 1; i <= affectedRFQCasesCount ; i++) 
        { 
            PurchRFQCaseId rfqCaseId = conPeek(opportunityData, i); 
            details += rfqCaseId + '\n'; 
        } 
    } 

    return details; 
}
```

De två återstående abstrakta metoder att implementera är **provideHealingAction** och **securityMenuItem**. 

**provideHealingAction** returnerar ett sant värde om en självläkande åtgärd tillhandahålls, annars returneras ett falskt värde. Om ett sant värde returneras måste metoden **performAction** implementeras, annars uppstår ett fel. Metoden **performAction** tar argumentet **SelfHealingOpportunity** i vilken data kan användas för åtgärden. I exemplet öppnar åtgärden **PurchRFQCaseTableListPage** för manuell korrigering. 

```xpp
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

Beroende på specifik regel, kan det vara möjligt att anta en automatisk åtgärd med affärsmöjligheten. I det här exemplet skulle systemet kunna generera rubriker för anbudsförfrågan automatiskt. 

**securityMenuItem** returnerar namnet på ett menyalternativ så att regeln endast är synlig för användare som har åtkomst till menyalternativet. För säkerhets skulls krävs kanske att särskilda regler och affärsmöjligheter endast är tillgängliga för auktoriserade användare. I exemplet kan endast användare med tillgång till **PurchRFQCaseTitleAction** se affärsmöjligheten. Observera att det här menyalternativet för åtgärd skapades för det här exemplet och har lagts till som en startpunkt för säkerhetsprivilegiet **PurchRFQCaseTableMaintain**. 

> [!NOTE]
> Menyalternativet måste vara ett åtgärdsalternativ för säkerhet för att fungera korrekt. Andra typer av menyalternativ, som **visa menyalternativ** kommer inte att fungera.

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

När regeln har kompilerats körs följande jobb för att se den i användargränssnittet (UI).

```xpp
class ScanNewRulesJob 
{         
    public static void main(Args _args) 
    {         
        SysExtensionCache::clearAllScopes(); 
        var controller = new DiagnosticsRuleController(); 
        controller.runOperation(); 
    } 
} 
```

Regeln visas i formuläret **diagnostikregel validering** från **systemadministration** > **periodiska uppgifter** > **Underhåll diagnostikregel – validering**. För att utvärdera den gå till **systemadministration** > **periodiska uppgifter** > **Diagnostikregel – validering av tidsplan**. Välj frekvens för regeln, till exempel **daglig**. Klicka på **OK**. Gå till **systemadministration** > **Optimization advisor** för att se den nya affärsmöjligheten. 

Följande exempel är ett kodstycke med basen för en regel som inkluderar alla metoder och attribut som behövs. Det hjälper dig att komma igång med att skriva nya regler. Etiketter och åtgärdsalternativ som används i exemplet är endast i demonstrationssyfte.

```xpp
[DiagnosticsRuleAttribute]
public final class SkeletonSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule
{
    [DiagnosticsRuleSubscription(DiagnosticsArea::SCM,
                                 "@SkeletonRuleLabels:SkeletonRuleTitle", // Label with the title of the rule
                                 DiagnosticsRunFrequency::Monthly,
                                 "@SkeletonRuleLabels:SkeletonRuleDescription")] // Label with a description of the rule
    public str opportunityTitle()
    {
        // Return a label with the title of the opportunity
        return "@SkeletonRuleLabels:SkeletonOpportunityTitle";
    }

    public str opportunityDetails(SelfHealingOpportunity _opportunity)
    {
        str details = "";

        // Use _opportunity.data to provide details on the opportunity

        return details;
    }

    protected List evaluate()
    {
        List results = new List(Types::Record);

        // Write here the core logic of the rule

        // When creating an opportunity, use:
        //     * this.getOpportunityForCompany() for company specific opportunities
        //     * this.getOpportunityAcrossCompanies() for cross-company opportunities

        return results;
    }

    public boolean providesHealingAction()
    {
        return true;
    }

    protected void performAction(SelfHealingOpportunity _opportunity)
    {
        // Place here the code that performs the healing action

        // To open a form, use the following:
        // new MenuFunction(menuItemDisplayStr(SkeletonRuleDisplayMenuItem), MenuItemType::Display).run();
    }

    public MenuName securityMenuItem()
    {
        return menuItemActionStr(SkeletonRuleActionMenuItem);
    }

}
```

Mer information, se den korta YouTube-video: [klassificering av optimering i Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]