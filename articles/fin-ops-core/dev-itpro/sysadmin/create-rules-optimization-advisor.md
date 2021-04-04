---
title: Skapa regler för Optimization advisor
description: Det här avsnittet beskriver hur du lägger till nya regler Optimization advisor.
author: roxanadiaconu
manager: AnnBe
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
ms.openlocfilehash: 67e740a1e00c425f0e09b5f0fc960cf2778efd89
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568296"
---
# <a name="create-rules-for-optimization-advisor"></a><span data-ttu-id="a13c9-103">Skapa regler för Optimization advisor</span><span class="sxs-lookup"><span data-stu-id="a13c9-103">Create rules for Optimization advisor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a13c9-104">Det här avsnittet beskriver hur du lägger till nya regler i **Optimization advisor**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-104">This topic explains how to create new rules for **Optimization advisor**.</span></span> <span data-ttu-id="a13c9-105">Du kan till exempel skapa en ny regel som identifierar vilka anbudsförfrågningar (RFQ) som har en tom rubrik.</span><span class="sxs-lookup"><span data-stu-id="a13c9-105">For example, you can create a new rule that identifies which Request for Quotations (RFQ) cases have an empty title.</span></span> <span data-ttu-id="a13c9-106">Att använda titlar på ärenden gör dem lätta att känna igen och sökbara.</span><span class="sxs-lookup"><span data-stu-id="a13c9-106">Using titles on cases makes them easily identifiable and searchable.</span></span> <span data-ttu-id="a13c9-107">Även om exemplet är ganska enkelt visar det vad som kan uppnås med optimeringsregler.</span><span class="sxs-lookup"><span data-stu-id="a13c9-107">While quite simple, this example shows what can be achieved with optimization rules.</span></span> 

<span data-ttu-id="a13c9-108">A *regel* är en kontroll av programdata.</span><span class="sxs-lookup"><span data-stu-id="a13c9-108">A *rule* is a check on application data.</span></span> <span data-ttu-id="a13c9-109">Om villkoret som regeln beräknar uppfylls skapas möjligheter att optimera processer och förbättra data.</span><span class="sxs-lookup"><span data-stu-id="a13c9-109">If the condition that the rule evaluates is met, opportunities to optimize processes or improve data are created.</span></span> <span data-ttu-id="a13c9-110">Möjligheterna kan utnyttjas och, vid behov, kan inverkan av åtgärderna mätas.</span><span class="sxs-lookup"><span data-stu-id="a13c9-110">The opportunities can be acted upon and, optionally, the impact of the actions can be measured.</span></span> 

<span data-ttu-id="a13c9-111">Så här skapar du en ny regel för **Optimization advisor**. Lägg till en ny klass som utökar den abstrakta klassen **SelfHealingRule** och implementera gränssnittet **IDiagnosticsRule** som dekoreras med attributet **DiagnosticRule**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-111">To create a new rule for the **Optimization advisor**, add a new class that extends the **SelfHealingRule** abstract class, implements the **IDiagnosticsRule** interface, and is decorated by the **DiagnosticRule** attribute.</span></span> <span data-ttu-id="a13c9-112">Klassen måste också ha en metod som dekoreras med attributet **DiagnosticsRuleSubscription**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-112">The class must also have a method decorated with the **DiagnosticsRuleSubscription** attribute.</span></span> <span data-ttu-id="a13c9-113">Enligt praxis görs detta i metoden **opportunityTitle**, som beskrivs senare.</span><span class="sxs-lookup"><span data-stu-id="a13c9-113">By convention, that is done on the **opportunityTitle** method, which will be discussed later.</span></span> <span data-ttu-id="a13c9-114">Denna nya klass kan läggas till en anpassad modell med ett beroende av modellen **SelfHealingRules**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-114">This new class can be added to a custom model with a dependency on the **SelfHealingRules** model.</span></span> <span data-ttu-id="a13c9-115">I följande exempel kallas den regel som implementeras **RFQTitleSelfHealingRule**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-115">In the following example, the rule being implemented is called **RFQTitleSelfHealingRule**.</span></span>

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

<span data-ttu-id="a13c9-116">Den abstrakta klassen **SelfHealingRule** har metoder som måste implementeras i ärvda klasser.</span><span class="sxs-lookup"><span data-stu-id="a13c9-116">The **SelfHealingRule** abstract class has abstract methods that must be implemented in inheriting classes.</span></span> <span data-ttu-id="a13c9-117">Kärnan är **utvärderingsmetoden** som returnerar en lista över de affärsmöjligheter som har identifierats av regeln.</span><span class="sxs-lookup"><span data-stu-id="a13c9-117">The core is the **evaluate** method, which returns a list of the opportunities identified by the rule.</span></span> <span data-ttu-id="a13c9-118">Affärsmöjligheter kan vara per juridisk person eller kan gälla för hela systemet.</span><span class="sxs-lookup"><span data-stu-id="a13c9-118">Opportunities can be per legal entity or can apply to the whole system.</span></span>

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

<span data-ttu-id="a13c9-119">Metoden ovan loopar över företag och väljer anbudsförfrågningar med tom rubrik i metoden **findRFQCasesWithEmptyTitle**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-119">The method shown above loops over companies and selects RFQ cases with empty titles in the **findRFQCasesWithEmptyTitle** method.</span></span> <span data-ttu-id="a13c9-120">Om minst ett sådant fall hittas, skapas en företagsspecifik affärsmöjlighet med metoden **getOpportunityForCompany**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-120">If at least one such case is found, then a company-specific opportunity is created with the **getOpportunityForCompany** method.</span></span> <span data-ttu-id="a13c9-121">Lägg märke till att fältet **Data** i tabellen **SelfHealingOpportunity** är av typen **behållare** och därför kan innehålla all information som berör logiken för regeln.</span><span class="sxs-lookup"><span data-stu-id="a13c9-121">Notice that the field **Data** in the **SelfHealingOpportunity** table is of type **Container**, and can therefore contain any data relevant to the logic specific to this rule.</span></span> <span data-ttu-id="a13c9-122">Att ställa in **OpportunityDate** med aktuell tidsstämpel registrerar tidpunkten för den senaste utvärderingen av affärsmöjligheten.</span><span class="sxs-lookup"><span data-stu-id="a13c9-122">Setting **OpportunityDate** with the current timestamp registers the time of the latest evaluation of the opportunity.</span></span>  

<span data-ttu-id="a13c9-123">Affärsmöjligheter kan också vara mellan företag.</span><span class="sxs-lookup"><span data-stu-id="a13c9-123">Opportunities can also be cross-company.</span></span> <span data-ttu-id="a13c9-124">I detta fall behövs inte loopen över företag och affärsmöjligheten måste skapas med metoden **getOpportunityAcrossCompanies**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-124">In this case, the loop over companies is not necessary and the opportunity must be created with the **getOpportunityAcrossCompanies** method.</span></span> 

<span data-ttu-id="a13c9-125">Följande kod visar metoden **findRFQCasesWithEmptyTitle** som returnerar ID för de anbudsförfrågor som har tomma titlar.</span><span class="sxs-lookup"><span data-stu-id="a13c9-125">The following code shows the **findRFQCasesWithEmptyTitle** method, which returns the IDs of the RFQ cases that have empty titles.</span></span>

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

<span data-ttu-id="a13c9-126">Två ytterligare metoder som måste implementeras är **opportunityTitle** och **opportunityDetails**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-126">Two more methods that must be implemented are **opportunityTitle** and **opportunityDetails**.</span></span> <span data-ttu-id="a13c9-127">Det förra returnerar en kort rubrik för affärsmöjligheten, den senare returnerar en detaljerad beskrivning av affärsmöjligheten, som även kan innehålla data.</span><span class="sxs-lookup"><span data-stu-id="a13c9-127">The former returns a short title for the opportunity, the latter returns a detailed description of the opportunity, which can also include data.</span></span>

<span data-ttu-id="a13c9-128">Den rubrik som returneras av **opportunityTitle** visas i kolumnen **Optimeringsmöjlighet** i arbetsytan **Optimerings-advisor**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-128">The title returned by **opportunityTitle** appears under the **Optimization opportunity** column in the **Optimization advisor** workspace.</span></span> <span data-ttu-id="a13c9-129">Den visas också som rubrik i det sidofönster som visar mer information om affärsmöjligheten.</span><span class="sxs-lookup"><span data-stu-id="a13c9-129">It also appears as the header of the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="a13c9-130">Enligt praxis dekoreras den här metoden med attributet **DiagnosticRuleSubscription** som har följande argument:</span><span class="sxs-lookup"><span data-stu-id="a13c9-130">By convention, this method is decorated with the **DiagnosticRuleSubscription** attribute, which takes the following arguments:</span></span> 

* <span data-ttu-id="a13c9-131">**Diagnosområde** – en uppräkning av typen **DiagnosticArea** som beskriver vilket tillämpningsområde regeln tillhör t.ex. **DiagnosticArea::SCM**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-131">**Diagnostic area** – An enum of type **DiagnosticArea** that describes what area of the application the rule belongs to, such as **DiagnosticArea::SCM**.</span></span> 

* <span data-ttu-id="a13c9-132">**Regelnamn** – en sträng med regelnamn.</span><span class="sxs-lookup"><span data-stu-id="a13c9-132">**Rule name** – A string with the rule name.</span></span> <span data-ttu-id="a13c9-133">Namnet visas i kolumnen **Regelnamn** i formuläret **Diagnostikregel – validering** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="a13c9-133">This will appear under the **Rule name** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

* <span data-ttu-id="a13c9-134">**Körningsfrekvens** – en uppräkning av typen **DiagnosticRunFrequency** som beskriver hur ofta regeln ska köras **DiagnosticRunFrequency::Daily**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-134">**Run frequency** – An enum of type **DiagnosticRunFrequency** that describes how often the rule should be run, such as **DiagnosticRunFrequency::Daily**.</span></span> 

* <span data-ttu-id="a13c9-135">**Regelbeskrivning** – en sträng med en mer detaljerad beskrivning av regeln.</span><span class="sxs-lookup"><span data-stu-id="a13c9-135">**Rule description** – A string with a more detailed description of the rule.</span></span> <span data-ttu-id="a13c9-136">Namnet visas i kolumnen **Regelbeskrivning** i formuläret **Diagnostikregel – validering** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="a13c9-136">This will appear under the **Rule description** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

> [!NOTE]
> <span data-ttu-id="a13c9-137">Attributet **DiagnosticRuleSubscription** krävs för att reglerna ska fungera.</span><span class="sxs-lookup"><span data-stu-id="a13c9-137">The **DiagnosticRuleSubscription** attribute is required for the rule to work.</span></span> <span data-ttu-id="a13c9-138">Det används vanligtvis i **opportunityTitle** men kan dekorera alla metoder i klassen.</span><span class="sxs-lookup"><span data-stu-id="a13c9-138">Typically, it is used on **opportunityTitle**, but it can decorate any method of the class.</span></span>

<span data-ttu-id="a13c9-139">Nedan finns ett exempel på implementering.</span><span class="sxs-lookup"><span data-stu-id="a13c9-139">The following is an example implementation.</span></span> <span data-ttu-id="a13c9-140">Råa strängar används för enkel hantering, men en korrekt implementering kräver etiketter.</span><span class="sxs-lookup"><span data-stu-id="a13c9-140">Raw strings are used for simplicity, but a correct implementation requires labels.</span></span> 

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

<span data-ttu-id="a13c9-141">Beskrivningen som returneras av **opportunityDetails** visas i det sidofönster som visar mer information om affärsmöjligheten.</span><span class="sxs-lookup"><span data-stu-id="a13c9-141">The description returned by **opportunityDetails** appears on the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="a13c9-142">Detta tar argumentet **SelfHealingOpportunity**, som är fältet **Data** och som kan användas för att ge mer information om affärsmöjligheten.</span><span class="sxs-lookup"><span data-stu-id="a13c9-142">This takes the **SelfHealingOpportunity** argument, which is **Data** field that can be used to provide more details about the opportunity.</span></span> <span data-ttu-id="a13c9-143">I exemplet returnerar metoden ID på de anbudsförfrågor som har en tom rubrik.</span><span class="sxs-lookup"><span data-stu-id="a13c9-143">In the example, the method returns the IDs of the RFQ cases with an empty title.</span></span> 

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

<span data-ttu-id="a13c9-144">De två återstående abstrakta metoder att implementera är **provideHealingAction** och **securityMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-144">The two remaining abstract methods to implement are **provideHealingAction** and **securityMenuItem**.</span></span> 

<span data-ttu-id="a13c9-145">**provideHealingAction** returnerar ett sant värde om en självläkande åtgärd tillhandahålls, annars returneras ett falskt värde.</span><span class="sxs-lookup"><span data-stu-id="a13c9-145">**provideHealingAction** returns true if a healing action is provided, otherwise, it returns false.</span></span> <span data-ttu-id="a13c9-146">Om ett sant värde returneras måste metoden **performAction** implementeras, annars uppstår ett fel.</span><span class="sxs-lookup"><span data-stu-id="a13c9-146">If true is returned, the method **performAction** must be implemented, or an error will be thrown.</span></span> <span data-ttu-id="a13c9-147">Metoden **performAction** tar argumentet **SelfHealingOpportunity** i vilken data kan användas för åtgärden.</span><span class="sxs-lookup"><span data-stu-id="a13c9-147">The **performAction** method takes a **SelfHealingOpportunity** argument, in which the data can be used for the action.</span></span> <span data-ttu-id="a13c9-148">I exemplet öppnar åtgärden **PurchRFQCaseTableListPage** för manuell korrigering.</span><span class="sxs-lookup"><span data-stu-id="a13c9-148">In the example, the action opens the **PurchRFQCaseTableListPage**, for manual correction.</span></span> 

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

<span data-ttu-id="a13c9-149">Beroende på specifik regel, kan det vara möjligt att anta en automatisk åtgärd med affärsmöjligheten.</span><span class="sxs-lookup"><span data-stu-id="a13c9-149">Depending on the specifics of the rule, it might be possible to take an automatic action using the opportunity data.</span></span> <span data-ttu-id="a13c9-150">I det här exemplet skulle systemet kunna generera rubriker för anbudsförfrågan automatiskt.</span><span class="sxs-lookup"><span data-stu-id="a13c9-150">In this example, the system could generate titles for RFQ cases automatically.</span></span> 

<span data-ttu-id="a13c9-151">**securityMenuItem** returnerar namnet på ett menyalternativ så att regeln endast är synlig för användare som har åtkomst till menyalternativet.</span><span class="sxs-lookup"><span data-stu-id="a13c9-151">**securityMenuItem** returns the name of an action menu item such that the rule is only visible to users who can access the action menu item.</span></span> <span data-ttu-id="a13c9-152">För säkerhets skulls krävs kanske att särskilda regler och affärsmöjligheter endast är tillgängliga för auktoriserade användare.</span><span class="sxs-lookup"><span data-stu-id="a13c9-152">Security might require that specific rules and opportunities are accessible only to authorized users.</span></span> <span data-ttu-id="a13c9-153">I exemplet kan endast användare med tillgång till **PurchRFQCaseTitleAction** se affärsmöjligheten.</span><span class="sxs-lookup"><span data-stu-id="a13c9-153">In the example, only users with access to **PurchRFQCaseTitleAction** can view the opportunity.</span></span> <span data-ttu-id="a13c9-154">Observera att det här menyalternativet för åtgärd skapades för det här exemplet och har lagts till som en startpunkt för säkerhetsprivilegiet **PurchRFQCaseTableMaintain**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-154">Notice that this action menu item was created for this example, and was added as an entry point for the **PurchRFQCaseTableMaintain** security privilege.</span></span> 

> [!NOTE]
> <span data-ttu-id="a13c9-155">Menyalternativet måste vara ett åtgärdsalternativ för säkerhet för att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="a13c9-155">The menu item must be an action menu item for security to work correctly.</span></span> <span data-ttu-id="a13c9-156">Andra typer av menyalternativ, som **visa menyalternativ** kommer inte att fungera.</span><span class="sxs-lookup"><span data-stu-id="a13c9-156">Other menu item types, such as **Display menu items** will not work correctly.</span></span>

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

<span data-ttu-id="a13c9-157">När regeln har kompilerats körs följande jobb för att se den i användargränssnittet (UI).</span><span class="sxs-lookup"><span data-stu-id="a13c9-157">After the rule has compiled, execute the following job to have it display in the user interface (UI).</span></span>

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

<span data-ttu-id="a13c9-158">Regeln visas i formuläret **diagnostikregel validering** från **systemadministration** > **periodiska uppgifter** > **Underhåll diagnostikregel – validering**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-158">The rule will display in the **Diagnostics validation rule** form, available from **System administration** > **Periodic tasks** > **Maintain diagnostics validation rule**.</span></span> <span data-ttu-id="a13c9-159">För att utvärdera den gå till **systemadministration** > **periodiska uppgifter** > **Diagnostikregel – validering av tidsplan**. Välj frekvens för regeln, till exempel **daglig**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-159">To have it evaluated, go to **System administration** > **Periodic tasks** > **Schedule diagnostics validation rule**, select the frequency of the rule, such as **Daily**.</span></span> <span data-ttu-id="a13c9-160">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a13c9-160">Click **OK**.</span></span> <span data-ttu-id="a13c9-161">Gå till **systemadministration** > **Optimization advisor** för att se den nya affärsmöjligheten.</span><span class="sxs-lookup"><span data-stu-id="a13c9-161">Go to **System administration** > **Optimization advisor** to view the new opportunity.</span></span> 

<span data-ttu-id="a13c9-162">Följande exempel är ett kodstycke med basen för en regel som inkluderar alla metoder och attribut som behövs.</span><span class="sxs-lookup"><span data-stu-id="a13c9-162">The following example is a code snippet with the skeleton of a rule including all the required methods and attributes.</span></span> <span data-ttu-id="a13c9-163">Det hjälper dig att komma igång med att skriva nya regler.</span><span class="sxs-lookup"><span data-stu-id="a13c9-163">It helps you get started with writing new rules.</span></span> <span data-ttu-id="a13c9-164">Etiketter och åtgärdsalternativ som används i exemplet är endast i demonstrationssyfte.</span><span class="sxs-lookup"><span data-stu-id="a13c9-164">The labels and action menu items that are used in the example are only used for demonstration purpose.</span></span>

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

<span data-ttu-id="a13c9-165">Mer information, se den korta YouTube-video: [klassificering av optimering i Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span><span class="sxs-lookup"><span data-stu-id="a13c9-165">For more information, watch the short YouTube video: [Optimization advisor in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]