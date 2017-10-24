---
title: "Utforma en enkät"
description: "Det här avsnittet beskriver processen för att skapa en enkät. Det första steget är att utforma enkäten. Om du utformar en enkät skapar du inte bara frågorna och svaren, utan även strukturen som gör det möjligt att registrera och ordna svar i tabeller."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KCMCollectionType, KMAnswerCollection, KMCollection
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17341
ms.assetid: b27e2f12-c7a0-4a54-b8d8-17819f8a1c72
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 65720297b43af49d8c8382ee2e3dde903d05ed14
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="design-a-questionnaire"></a><span data-ttu-id="1b40f-105">Utforma en enkät</span><span class="sxs-lookup"><span data-stu-id="1b40f-105">Design a questionnaire</span></span>

<span data-ttu-id="1b40f-106">Det här avsnittet beskriver processen för att skapa en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-106">This topic describes the process for creating a questionnaire.</span></span> <span data-ttu-id="1b40f-107">Det första steget är att utforma enkäten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-107">The first step is to design the questionnaire.</span></span> <span data-ttu-id="1b40f-108">Om du utformar en enkät skapar du inte bara frågorna och svaren, utan även strukturen som gör det möjligt att registrera och ordna svar i tabeller.</span><span class="sxs-lookup"><span data-stu-id="1b40f-108">When you design a questionnaire, you not only write the questions and answers, but also create the structure that enables answers to be recorded and tabulated.</span></span> 

<span data-ttu-id="1b40f-109">En noggrant utformad enkät ökar kvaliteten på informationen som du samlar in.</span><span class="sxs-lookup"><span data-stu-id="1b40f-109">A carefully designed questionnaire can help increase the quality of the data that you collect.</span></span> <span data-ttu-id="1b40f-110">Med noggrann utformning är det lättare att du välja lämpliga alternativ vid en lämplig tidpunkt för en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-110">Through careful design, you can better select the appropriate options at the appropriate time for a questionnaire.</span></span> <span data-ttu-id="1b40f-111">Följande punkter kan hjälpa dig att planera en effektiv enkät:</span><span class="sxs-lookup"><span data-stu-id="1b40f-111">The following points can help you plan an effective questionnaire:</span></span>

-   <span data-ttu-id="1b40f-112">Definierar tydligt syftet med enkäten för att garantera att frågorna stöder syftet.</span><span class="sxs-lookup"><span data-stu-id="1b40f-112">Clearly define the purpose of the questionnaire to help guarantee that the questions support the purpose.</span></span>
-   <span data-ttu-id="1b40f-113">Bestäm vilken person eller vilken grupp personer som du vill ska fylla i enkäten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-113">Determine the individual person or the group of people who should complete the questionnaire.</span></span>
-   <span data-ttu-id="1b40f-114">Skriv frågor som visas i enkäten och inkludera svarsalternativ om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="1b40f-114">Write questions that will appear on the questionnaire, and include answer choices, if applicable.</span></span>
-   <span data-ttu-id="1b40f-115">Kontrollera att enkäten är logiskt så att svarande förblir engagerade.</span><span class="sxs-lookup"><span data-stu-id="1b40f-115">Be sure that the questionnaire flows logically, so that respondents remain engaged.</span></span>
-   <span data-ttu-id="1b40f-116">Ordna frågor och svar i den ordning som de visas för svarande.</span><span class="sxs-lookup"><span data-stu-id="1b40f-116">Arrange questions and answers in the order that they should be presented to respondents in.</span></span>
-   <span data-ttu-id="1b40f-117">Bestäm hur resultatet utvärderas, om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="1b40f-117">Decide how the results should be evaluated, if applicable.</span></span>
-   <span data-ttu-id="1b40f-118">Välj om du behöver ytterligare funktioner.</span><span class="sxs-lookup"><span data-stu-id="1b40f-118">Decide whether you’ll need additional features.</span></span> <span data-ttu-id="1b40f-119">Bestäm till exempel om och hur resultat kategoriseras, om det krävs en tidsgräns eller om alla frågor ska vara obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="1b40f-119">For example, determine whether and how results should be categorized, whether a time limit is required, or whether all the questions will be mandatory.</span></span>

<span data-ttu-id="1b40f-120">Designfasen innehåller fyra uppgiftskategorier du måste slutföra i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="1b40f-120">The design phase includes four categories of tasks that you must complete in this order:</span></span>

1.  <span data-ttu-id="1b40f-121">Nödvändiga inställningar efter behov.</span><span class="sxs-lookup"><span data-stu-id="1b40f-121">Set up prerequisites, as required.</span></span>
2.  <span data-ttu-id="1b40f-122">Skapa svarsgrupper och svar, om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="1b40f-122">Set up answer groups and answers, if applicable.</span></span>
3.  <span data-ttu-id="1b40f-123">Skapa frågor och deras koppling till svarsgrupperna.</span><span class="sxs-lookup"><span data-stu-id="1b40f-123">Set up questions and their association with the answer groups.</span></span>
4.  <span data-ttu-id="1b40f-124">Skapa själva enkäten och koppla frågor till den.</span><span class="sxs-lookup"><span data-stu-id="1b40f-124">Set up the questionnaire itself, and attach questions to it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1b40f-125">Krav</span><span class="sxs-lookup"><span data-stu-id="1b40f-125">Prerequisites</span></span>
<span data-ttu-id="1b40f-126">Vissa förutsättningar måste vara finnas innan du kan skapa enkäter, frågor och svar.</span><span class="sxs-lookup"><span data-stu-id="1b40f-126">Some prerequisites must be in place before you can create questionnaires, answers, and questions.</span></span> <span data-ttu-id="1b40f-127">Dock krävs inte alla förutsättningar för fullständig funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="1b40f-127">However, not all prerequisites are required for full functionality.</span></span>

### <a name="required"></a><span data-ttu-id="1b40f-128">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="1b40f-128">Required</span></span>

| <span data-ttu-id="1b40f-129">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="1b40f-129">Prerequisite</span></span>        | <span data-ttu-id="1b40f-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1b40f-130">Description</span></span>                |
|---------------------|----------------------------|
| <span data-ttu-id="1b40f-131">Enkättyper</span><span class="sxs-lookup"><span data-stu-id="1b40f-131">Questionnaire types</span></span> | <span data-ttu-id="1b40f-132">Kategorisera enkäter.</span><span class="sxs-lookup"><span data-stu-id="1b40f-132">Categorize questionnaires.</span></span> |
| <span data-ttu-id="1b40f-133">Frågetyper</span><span class="sxs-lookup"><span data-stu-id="1b40f-133">Question types</span></span>      | <span data-ttu-id="1b40f-134">Kategorisera frågor.</span><span class="sxs-lookup"><span data-stu-id="1b40f-134">Categorize questions.</span></span>      |

### <a name="optional"></a><span data-ttu-id="1b40f-135">Valfri</span><span class="sxs-lookup"><span data-stu-id="1b40f-135">Optional</span></span>

| <span data-ttu-id="1b40f-136">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="1b40f-136">Prerequisite</span></span>             | <span data-ttu-id="1b40f-137">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1b40f-137">Description</span></span>                                                    |
|--------------------------|----------------------------------------------------------------|
| <span data-ttu-id="1b40f-138">Enkätparametrar</span><span class="sxs-lookup"><span data-stu-id="1b40f-138">Questionnaire parameters</span></span> | <span data-ttu-id="1b40f-139">Ändra grundläggande kontroller och standardinställningar för enkäter.</span><span class="sxs-lookup"><span data-stu-id="1b40f-139">Modify basic controls and default settings for questionnaires.</span></span> |

### <a name="questionnaire-types"></a><span data-ttu-id="1b40f-140">Enkättyper</span><span class="sxs-lookup"><span data-stu-id="1b40f-140">Questionnaire types</span></span>

<span data-ttu-id="1b40f-141">Enkättyper krävs och måste ha tilldelats när du skapar en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-141">Questionnaire types are required and must be assigned when you create a questionnaire.</span></span> <span data-ttu-id="1b40f-142">Enkättyper hjälpa dig att hantera och klassificera enkäter enklare.</span><span class="sxs-lookup"><span data-stu-id="1b40f-142">Questionnaire types help you manage and classify questionnaires more easily.</span></span> <span data-ttu-id="1b40f-143">Använd enkättyper för att klassificera enkäter och skilja dem från varandra.</span><span class="sxs-lookup"><span data-stu-id="1b40f-143">Use questionnaire types to classify questionnaires and differentiate them from each other.</span></span> <span data-ttu-id="1b40f-144">Om du till exempel har flera enkäter att välja bland, kan du filtrera dem efter typ för att göra det enklare att hitta en viss enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-144">For example, if you have multiple questionnaires to select from, you can filter them by type to help make it easier to find a particular questionnaire.</span></span> <span data-ttu-id="1b40f-145">Här följer några exempel på enkättyper:</span><span class="sxs-lookup"><span data-stu-id="1b40f-145">Here are some examples of questionnaire types:</span></span>

-   <span data-ttu-id="1b40f-146">Personalutveckling</span><span class="sxs-lookup"><span data-stu-id="1b40f-146">Human resource development</span></span>
-   <span data-ttu-id="1b40f-147">Kundenkäter</span><span class="sxs-lookup"><span data-stu-id="1b40f-147">Customer surveys</span></span>
-   <span data-ttu-id="1b40f-148">Granska process</span><span class="sxs-lookup"><span data-stu-id="1b40f-148">Review process</span></span>

### <a name="question-types"></a><span data-ttu-id="1b40f-149">Frågetyper</span><span class="sxs-lookup"><span data-stu-id="1b40f-149">Question types</span></span>

<span data-ttu-id="1b40f-150">Enkättyper krävs och måste ha tilldelats när du skapar en fråga.</span><span class="sxs-lookup"><span data-stu-id="1b40f-150">Question types are required and must be assigned when you create a question.</span></span> 

<span data-ttu-id="1b40f-151">Använd frågetyper om du vill kategorisera frågor för rapportering.</span><span class="sxs-lookup"><span data-stu-id="1b40f-151">Use question types to categorize questions for reporting.</span></span> <span data-ttu-id="1b40f-152">Frågetyper gör det även enklare att hitta frågor, eftersom du kan använda typer som filter på sidan **Frågor**.</span><span class="sxs-lookup"><span data-stu-id="1b40f-152">Question types also make it easier to find questions, because you can use types as filters on the **Questions** page.</span></span> <span data-ttu-id="1b40f-153">Här följer några exempel på frågetyper:</span><span class="sxs-lookup"><span data-stu-id="1b40f-153">Here are some examples of question types:</span></span>

-   <span data-ttu-id="1b40f-154">Personal</span><span class="sxs-lookup"><span data-stu-id="1b40f-154">Human resource</span></span>
-   <span data-ttu-id="1b40f-155">Hantera affärer</span><span class="sxs-lookup"><span data-stu-id="1b40f-155">Managing business</span></span>
-   <span data-ttu-id="1b40f-156">Kursutvärdering</span><span class="sxs-lookup"><span data-stu-id="1b40f-156">Course evaluation</span></span>

### <a name="questionnaire-parameters"></a><span data-ttu-id="1b40f-157">Enkätparametrar</span><span class="sxs-lookup"><span data-stu-id="1b40f-157">Questionnaire parameters</span></span>

<span data-ttu-id="1b40f-158">Enkätparametrar är valfria.</span><span class="sxs-lookup"><span data-stu-id="1b40f-158">Questionnaire parameters are optional.</span></span> <span data-ttu-id="1b40f-159">Du kanske inte använder dem, beroende på företagets behov.</span><span class="sxs-lookup"><span data-stu-id="1b40f-159">You might not use them, depending on your company’s requirements.</span></span> 

<span data-ttu-id="1b40f-160">Enkätparametrar definierar anonymitet, nummerseriekoder och referenstyperna för en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-160">Questionnaire parameters define the anonymity, number sequence codes, and reference types of a questionnaire.</span></span> <span data-ttu-id="1b40f-161">När en organisation distribuerar en enkät kan alternativet att låta svarande förbli anonyma vara viktigt.</span><span class="sxs-lookup"><span data-stu-id="1b40f-161">When an organization distributes a questionnaire, the option to allow respondents to remain anonymous might be of concern.</span></span> 

<span data-ttu-id="1b40f-162">Nummerseriekoderna används för att ordna frågor och svar.</span><span class="sxs-lookup"><span data-stu-id="1b40f-162">The number sequence codes are used to organize questions and answers.</span></span> <span data-ttu-id="1b40f-163">Baserat på nummerserierkoderna tilldelas värden automatiskt till objekt.</span><span class="sxs-lookup"><span data-stu-id="1b40f-163">Based on these number sequence codes, values are automatically assigned to items.</span></span> 

<span data-ttu-id="1b40f-164">Du bör definiera alla parametrar innan du börjar skapa dina data.</span><span class="sxs-lookup"><span data-stu-id="1b40f-164">You should define all parameters before you begin to create your data.</span></span> <span data-ttu-id="1b40f-165">Du kan ändra enkätparameterinställningarna när som helst.</span><span class="sxs-lookup"><span data-stu-id="1b40f-165">You can modify the questionnaire parameter settings at any time.</span></span>

## <a name="questionnaire-components"></a><span data-ttu-id="1b40f-166">Enkätkomponenter</span><span class="sxs-lookup"><span data-stu-id="1b40f-166">Questionnaire components</span></span>
<span data-ttu-id="1b40f-167">Frågeformulär består av tre huvuddelar: svarsgrupper som innehåller svaren på en flervalsfråga frågor, frågor i enkäten samt själva enkäten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-167">Questionnaires comprise three main elements: answer groups that contain the answers for multiple choice questions, questions, and the questionnaire itself.</span></span> <span data-ttu-id="1b40f-168">Du kan även gruppera frågorna i en enkät i resultatgrupper.</span><span class="sxs-lookup"><span data-stu-id="1b40f-168">You can optionally group the questions on a questionnaire into result groups.</span></span> <span data-ttu-id="1b40f-169">Resultatgrupper kategoriserar frågor och tillhandahåller ytterligare analys i enkäten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-169">Result groups let you categorize questions and provide further analysis on the questionnaire.</span></span> 

<span data-ttu-id="1b40f-170">[![QuestionnaireComponents](./media/questionnairecomponents-1024x615.png)](./media/questionnairecomponents.png)</span><span class="sxs-lookup"><span data-stu-id="1b40f-170">[![QuestionnaireComponents](./media/questionnairecomponents-1024x615.png)](./media/questionnairecomponents.png)</span></span>

### <a name="answer-groups-and-answers"></a><span data-ttu-id="1b40f-171">Svarsgrupper och svar</span><span class="sxs-lookup"><span data-stu-id="1b40f-171">Answer groups and answers</span></span>

<span data-ttu-id="1b40f-172">Svarande kan besvara en fråga på två sätt beroende på frågans ämne:</span><span class="sxs-lookup"><span data-stu-id="1b40f-172">Respondents can answer a question in two ways, depending on the subject of the question:</span></span>

-   <span data-ttu-id="1b40f-173">Öppna frågor kräver inte svar i ett specifikt format.</span><span class="sxs-lookup"><span data-stu-id="1b40f-173">Open-ended questions don’t require responses in a specific format.</span></span> <span data-ttu-id="1b40f-174">Svarande svara med text, ett tal, ett datum eller en tid.</span><span class="sxs-lookup"><span data-stu-id="1b40f-174">Respondents can type a response as text, a number, a date, or a time.</span></span> <span data-ttu-id="1b40f-175">Dessa frågor kräver vanligen att de svarande tillhandahåller subjektiv information i sina svar, till exempel en åsikt, en beskrivning, en värdering eller en uppskattning.</span><span class="sxs-lookup"><span data-stu-id="1b40f-175">These questions typically require that the respondents provide subjective information in their answers, such as an opinion, description, evaluation, or estimate.</span></span>
-   <span data-ttu-id="1b40f-176">Stänga frågor kräver att den svarande väljer ett svar på en lista över möjliga svar.</span><span class="sxs-lookup"><span data-stu-id="1b40f-176">Closed-ended questions require that the respondent select an answer in a list of possible correct answers.</span></span>

<span data-ttu-id="1b40f-177">Om du vill ge en lista med svar på stängda frågor kan du skapa svar på sidan **Svarsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="1b40f-177">To provide a list of possible answers for closed-ended questions, you can create answers on the **Answer groups** page.</span></span> 

<span data-ttu-id="1b40f-178">Svarsgrupper och svar är komponenter som utgör det huvudsakliga informationsmaterialet som frågor skapas från.</span><span class="sxs-lookup"><span data-stu-id="1b40f-178">Answer groups and answers are components that make up the main body of information that questions are created from.</span></span> <span data-ttu-id="1b40f-179">När du har skapat en svarsgrupp kan du koppla svarsgruppen till en fråga i fältet **Svarsgrupp** på sidan **Frågor**.</span><span class="sxs-lookup"><span data-stu-id="1b40f-179">After you create an answer group, you can associate the answer group with a question in the **Answer group** field on the **Questions** page.</span></span> 

<span data-ttu-id="1b40f-180">Samma svarsgrupp kan användas för fler frågor i samma enkät och den kan också användas i flera enkäter.</span><span class="sxs-lookup"><span data-stu-id="1b40f-180">An answer group can be used for more than one question on the same questionnaire, and can also be used on more than one questionnaire.</span></span> 

<span data-ttu-id="1b40f-181">**Anm.** Om du ändrar svarstext i svarsgrupper som redan har använts i ifyllda enkäter kan bli data svåra att utvärdera och enkätresultat gäller kanske inte längre.</span><span class="sxs-lookup"><span data-stu-id="1b40f-181">**Note:** If you modify answer text in answer groups that have already been used on completed questionnaires, data can become difficult to evaluate, and questionnaire results might no longer be valid.</span></span> <span data-ttu-id="1b40f-182">Om du måste ändra en svarsgrupp, bör du vill skapa en ny svarsgrupp i stället för att ändra en befintlig.</span><span class="sxs-lookup"><span data-stu-id="1b40f-182">If you must change an answer group, consider creating a new answer group instead of changing an existing one.</span></span> <span data-ttu-id="1b40f-183">Du kan inte radera svarsgrupper som har kopplats till en fråga eller ett svar eller som har besvarats.</span><span class="sxs-lookup"><span data-stu-id="1b40f-183">You can't delete answer groups that are attached to a question or answer, or that have been answered.</span></span>

### <a name="questions"></a><span data-ttu-id="1b40f-184">Frågor</span><span class="sxs-lookup"><span data-stu-id="1b40f-184">Questions</span></span>

<span data-ttu-id="1b40f-185">En enkät måste innehålla frågor.</span><span class="sxs-lookup"><span data-stu-id="1b40f-185">A questionnaire must contain questions.</span></span> <span data-ttu-id="1b40f-186">Frågor kan vara antingen öppna eller stängda.</span><span class="sxs-lookup"><span data-stu-id="1b40f-186">Questions can be either open-ended or closed-ended.</span></span>

-   <span data-ttu-id="1b40f-187">Svaren för öppna frågor kontrolleras inte och svarande kan skriva in sina svar.</span><span class="sxs-lookup"><span data-stu-id="1b40f-187">The responses to open-ended questions aren't controlled, and respondents can type their answers.</span></span>
-   <span data-ttu-id="1b40f-188">Stänga frågor kräver en lista med fördefinierade svarsalternativ och frågorna kan struktureras för att tillåta att svaranden väljer flera svar.</span><span class="sxs-lookup"><span data-stu-id="1b40f-188">Closed-ended questions require a list of predefined response options, and the questions can be structured to let a respondent select multiple responses.</span></span> <span data-ttu-id="1b40f-189">Frågor bör utformas för att få fram specifik information från en svarande och måste vara länkade till en svarsgrupp som innehåller svarsalternativen för varje stängd fråga.</span><span class="sxs-lookup"><span data-stu-id="1b40f-189">Questions should be designed to elicit specific information from a respondent and must be linked to an answer group that provides the response options for each closed-ended question.</span></span> 
     -  <span data-ttu-id="1b40f-190">**Anm.:** Innan du kan skapa stängda frågor måste du skapa svarsgrupper och svar.</span><span class="sxs-lookup"><span data-stu-id="1b40f-190">**Note:** Before you can set up closed-ended questions, you must create answer groups and answers.</span></span>

<span data-ttu-id="1b40f-191">Frågor kan grupperas i en villkorsstyrd frågehierarki så att sekundära frågor beror på svaren som den svarande valde för föregående fråga.</span><span class="sxs-lookup"><span data-stu-id="1b40f-191">Questions can be arranged in a conditional question hierarchy, so that secondary questions depend on the answer that the respondent selects for the previous question.</span></span> <span data-ttu-id="1b40f-192">Du kan skriva frågorna först och sedan flytta ordna dem till en hierarki senare.</span><span class="sxs-lookup"><span data-stu-id="1b40f-192">You can write the questions first and then arrange them into a hierarchy later.</span></span>

## <a name="setting-up-questionnaires"></a><span data-ttu-id="1b40f-193">Ställa in enkäter</span><span class="sxs-lookup"><span data-stu-id="1b40f-193">Setting up questionnaires</span></span>
<span data-ttu-id="1b40f-194">**Anm.:** Innan du kan ställa in en enkät måste du skapa frågor, svar och förutsättningar.</span><span class="sxs-lookup"><span data-stu-id="1b40f-194">**Note:** Before you can set up a questionnaire, you must set up answers, questions, and prerequisites.</span></span> 

<span data-ttu-id="1b40f-195">För varje enkät kan du ange följande information:</span><span class="sxs-lookup"><span data-stu-id="1b40f-195">For each questionnaire, you can specify the following information:</span></span>

-   <span data-ttu-id="1b40f-196">Den totala tiden eller tidsgränsen för svar på obligatoriska frågor.</span><span class="sxs-lookup"><span data-stu-id="1b40f-196">The total time or time limit to answer mandatory questions.</span></span>
-   <span data-ttu-id="1b40f-197">Om alla frågor är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="1b40f-197">Whether all questions are mandatory.</span></span>
-   <span data-ttu-id="1b40f-198">Att beräkna poäng i en enkät eller inte.</span><span class="sxs-lookup"><span data-stu-id="1b40f-198">Whether to calculate points on a questionnaire.</span></span>
-   <span data-ttu-id="1b40f-199">Hur du kategoriserar resultat.</span><span class="sxs-lookup"><span data-stu-id="1b40f-199">How to categorize results.</span></span>
-   <span data-ttu-id="1b40f-200">Om enkäten ska vara tillgänglig för en begränsad grupp svarande.</span><span class="sxs-lookup"><span data-stu-id="1b40f-200">Whether the questionnaire will be available to a restricted set of respondents.</span></span>
-   <span data-ttu-id="1b40f-201">Om en formulärmall visas som en bakgrund bakom varje sida i enkäten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-201">Whether a form template should be displayed as a background behind each page of the questionnaire.</span></span>
-   <span data-ttu-id="1b40f-202">Ytterligare kommentarer som krävs för att klargöra avsikten med enkäten för de svarande.</span><span class="sxs-lookup"><span data-stu-id="1b40f-202">Whether additional notes are required in order to clarify the intent of the questionnaire for the respondents.</span></span>
-   <span data-ttu-id="1b40f-203">Om du vill visa frågor i en viss ordningsföljd eller välja dem slumpvis från en pool.</span><span class="sxs-lookup"><span data-stu-id="1b40f-203">Whether to display questions in a fixed order or randomly select them from a pool.</span></span>
-   <span data-ttu-id="1b40f-204">Om frågor ställs endast om specifika svar har angetts för tidigare svar.</span><span class="sxs-lookup"><span data-stu-id="1b40f-204">Whether questions will be asked only if specific responses are given for previous answers.</span></span>

### <a name="set-up-a-questionnaire"></a><span data-ttu-id="1b40f-205">Ställ in en enkät</span><span class="sxs-lookup"><span data-stu-id="1b40f-205">Set up a questionnaire</span></span>

<span data-ttu-id="1b40f-206">Den primära sidan som du använder för att ställa in en enkät är **Enkäter**.</span><span class="sxs-lookup"><span data-stu-id="1b40f-206">The primary page that you use to set up a questionnaire is the **Questionnaires** page.</span></span> <span data-ttu-id="1b40f-207">Ställ in en enkät genom att slutföra följande uppgifter i ordningsföljd:</span><span class="sxs-lookup"><span data-stu-id="1b40f-207">To set up a questionnaire, complete the following tasks in order:</span></span>

1.  <span data-ttu-id="1b40f-208">Skapa en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-208">Create a questionnaire.</span></span>
2.  <span data-ttu-id="1b40f-209">Följ ett av dessa steg i för att koppla frågor till enkäten:</span><span class="sxs-lookup"><span data-stu-id="1b40f-209">Follow one of these steps to attach questions to the questionnaire:</span></span>
    -   <span data-ttu-id="1b40f-210">Om du använder resultatgrupper kan du koppla frågor till en enkät genom att använda resultatgrupper.</span><span class="sxs-lookup"><span data-stu-id="1b40f-210">If you're using result groups, you can attach questions to a questionnaire by using result groups.</span></span> <span data-ttu-id="1b40f-211">Ställ först in resultatgrupper för enkäten och lägg sedan till frågor till resultatgrupperna.</span><span class="sxs-lookup"><span data-stu-id="1b40f-211">First set up the result groups for the questionnaire, and then add questions to the result groups.</span></span>
    -   <span data-ttu-id="1b40f-212">Om du inte använder resultatgrupper kan du koppla frågor direkt till enkäten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-212">If you aren't using result groups, you can attach questions directly to the questionnaire.</span></span>

3.  <span data-ttu-id="1b40f-213">Ställ in en hierarki för villkorsfrågor om en sådan krävs.</span><span class="sxs-lookup"><span data-stu-id="1b40f-213">Set up a conditional question hierarchy, if it's required.</span></span>
4.  <span data-ttu-id="1b40f-214">Testa enkäten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-214">Test the questionnaire.</span></span>

<span data-ttu-id="1b40f-215">Klicka på **Validera** på sidan **Enkäter** för att testa om enkäten är korrekt sammanställd.</span><span class="sxs-lookup"><span data-stu-id="1b40f-215">On the **Questionnaires** page, click **Validate** to test whether the questionnaire is assembled correctly.</span></span> <span data-ttu-id="1b40f-216">Det är dock också praktiskt att fylla i enkäten och testa den själv innan du distribuerar den.</span><span class="sxs-lookup"><span data-stu-id="1b40f-216">However, it's also a good idea to complete the questionnaire and test it yourself before you distribute it.</span></span>

### <a name="modify-a-questionnaire"></a><span data-ttu-id="1b40f-217">Ändra en enkät</span><span class="sxs-lookup"><span data-stu-id="1b40f-217">Modify a questionnaire</span></span>

<span data-ttu-id="1b40f-218">På sidan **Enkäter** kan du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="1b40f-218">You can complete the following tasks on the **Questionnaires** page:</span></span>

-   <span data-ttu-id="1b40f-219">Redigera informationen i enkäten, inklusive resultatgrupper och frågor.</span><span class="sxs-lookup"><span data-stu-id="1b40f-219">Modify information in the questionnaire, such as the result groups and questions.</span></span>
-   <span data-ttu-id="1b40f-220">Radera och lägga till frågor.</span><span class="sxs-lookup"><span data-stu-id="1b40f-220">Delete and add questions.</span></span>
-   <span data-ttu-id="1b40f-221">Göra ändringar i resultgrupperna och sekvensnummer.</span><span class="sxs-lookup"><span data-stu-id="1b40f-221">Make changes in the result groups and sequence number.</span></span> 

<span data-ttu-id="1b40f-222">**Varning:** Var försiktig när du ändrar enkäter som redan har besvarats.</span><span class="sxs-lookup"><span data-stu-id="1b40f-222">**Caution:** Be careful when you change questionnaires that have already been answered.</span></span> <span data-ttu-id="1b40f-223">Ändringar kan minska noggrannheten i statistiken och gör dem till dålig grund för utvärdering.</span><span class="sxs-lookup"><span data-stu-id="1b40f-223">Changes can reduce the accuracy of statistics and therefore make them a poor basis for evaluation.</span></span> <span data-ttu-id="1b40f-224">Överväg att hellre skapa en ny fråga istället för att ändra en fråga som redan har besvarats.</span><span class="sxs-lookup"><span data-stu-id="1b40f-224">Consider creating a new question instead of changing a question that has already been answered.</span></span>

<span data-ttu-id="1b40f-225">I en enkät kan du inte ta bort följande typer av frågor:</span><span class="sxs-lookup"><span data-stu-id="1b40f-225">In a questionnaire, you can't delete the following types of questions:</span></span>

-   <span data-ttu-id="1b40f-226">Frågor som har kopplats till en enkät</span><span class="sxs-lookup"><span data-stu-id="1b40f-226">Questions that are attached to a questionnaire</span></span>
-   <span data-ttu-id="1b40f-227">Frågor som har besvarats och därför redan visas i dialogrutan **Svar**.</span><span class="sxs-lookup"><span data-stu-id="1b40f-227">Questions that have already been answered and therefore appear in the **Answers** dialog box.</span></span>

### <a name="result-groups"></a><span data-ttu-id="1b40f-228">Resultatgrupper</span><span class="sxs-lookup"><span data-stu-id="1b40f-228">Result groups</span></span>

<span data-ttu-id="1b40f-229">Resultatgrupper är valfria när du kopplar frågor till en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-229">Result groups are optional when you attach questions to a questionnaire.</span></span> 

<span data-ttu-id="1b40f-230">En resultatgrupp används för att beräkna poäng och kategorisera resultaten för en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-230">A result group is used to calculate points and categorize the results of a questionnaire.</span></span> <span data-ttu-id="1b40f-231">Om du använder resultatgrupper kan du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="1b40f-231">If you use result groups, you can perform the following tasks:</span></span>

-   <span data-ttu-id="1b40f-232">Utvärdera enkätresultat baserat på poängstatistik.</span><span class="sxs-lookup"><span data-stu-id="1b40f-232">Evaluate questionnaire results, based on point statistics.</span></span>
-   <span data-ttu-id="1b40f-233">Utvärdera den svarandes poäng för varje den resultatgrupp du ställer in.</span><span class="sxs-lookup"><span data-stu-id="1b40f-233">Evaluate a respondent’s score for each result group that you set up.</span></span>
-   <span data-ttu-id="1b40f-234">Generera statistik för varje resultatgrupp som hjälper dig att analysera resultaten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-234">Generate statistics for each result group to help you analyze results.</span></span>
-   <span data-ttu-id="1b40f-235">Skriv ut en rapport som visar resultat för varje resultatgrupp och valfria poäng/texter som baseras på poäng som erhållits i varje resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="1b40f-235">Print a report that shows results for each result group, and also optional points/texts that are based on points that are earned in each result group.</span></span>

<span data-ttu-id="1b40f-236">**Anm.:** Innan du kan ställa in resultatgrupper måste du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="1b40f-236">**Note:** Before you can set up result groups, you must complete the following tasks:</span></span>

-   <span data-ttu-id="1b40f-237">Skapa stängda frågor.</span><span class="sxs-lookup"><span data-stu-id="1b40f-237">Set up closed-ended questions.</span></span> <span data-ttu-id="1b40f-238">För stängd fråga måste ange indatatypen på sidan **Frågor** vara **Kryssruta**, **Alternativknapp** eller **Kombinationsruta**.</span><span class="sxs-lookup"><span data-stu-id="1b40f-238">For a closed-ended question, the input type on the **Questions** page must be **Check box**, **Alternative button**, or **Combo box**.</span></span>
-   <span data-ttu-id="1b40f-239">Definiera poäng för svaren i svarsgrupperna som är tilldelade till varje fråga.</span><span class="sxs-lookup"><span data-stu-id="1b40f-239">Define points for answers in the answer groups that are assigned to each question.</span></span>
-   <span data-ttu-id="1b40f-240">Ställ in en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-240">Set up a questionnaire.</span></span>

<span data-ttu-id="1b40f-241">Bifoga frågor till en enkät genom att använda resultatgrupper, genom att först lägga till resultatgrupper för enkäten och sedan lägga till frågor till resultatgrupperna.</span><span class="sxs-lookup"><span data-stu-id="1b40f-241">To attach questions to a questionnaire by using result groups, first set up the result groups for the questionnaire, and then add questions to the result groups.</span></span> <span data-ttu-id="1b40f-242">Om du inte använder resultatgrupper kan du koppla frågor direkt till enkäten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-242">If you don't use result groups, you can attach questions directly to a questionnaire.</span></span> 

<span data-ttu-id="1b40f-243">Du kan ställa in resultatgrupper för att bedöma hur många poäng som en svarande har i varje kategori.</span><span class="sxs-lookup"><span data-stu-id="1b40f-243">You can set up multiple result groups to evaluate the points that a respondent earns in each category.</span></span> <span data-ttu-id="1b40f-244">När en enkät har slutförts kan du visa hur många poäng som har uppnåtts för varje resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="1b40f-244">After a questionnaire is completed, you can view the points that have been achieved for each result group.</span></span> 

<span data-ttu-id="1b40f-245">**Tips:** Om du vill utvärdera en enkät genom att använda poäng men inte separata kategorier, kan du lägga till alla frågor i en enskild resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="1b40f-245">**Tip:** To evaluate a questionnaire by using points but not separate categories, you can add all questions to a single result group.</span></span> 

<span data-ttu-id="1b40f-246">För varje resultatgrupp kan du även skapa en eller flera poängbaserade meddelanden som svarande får när de har fyllt i en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-246">For each result group, you can also set up one or more point-based messages that respondents receive after they complete a questionnaire.</span></span> <span data-ttu-id="1b40f-247">Texten som visas kan variera beroende på poängen som en svarande får i en resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="1b40f-247">The text that is shown can vary, depending on the score that a respondent achieves in a result group.</span></span> <span data-ttu-id="1b40f-248">Använd poängbaserade meddelanden genom att definiera poängintervall och en beskrivning av varje intervall.</span><span class="sxs-lookup"><span data-stu-id="1b40f-248">To use point-based messages, you must define point intervals and a description of each interval.</span></span> <span data-ttu-id="1b40f-249">När en svarande uppnår en poäng i ett speciellt intervall inkluderas texten för det intervallet i resultatrapporten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-249">When a respondent achieves a score in a specific interval, the text for that interval is included on the results report.</span></span> 

<span data-ttu-id="1b40f-250">Eftersom en resultatgrupp är relaterad till poäng som är kopplade till specifika uppsättningar med frågor i en enkät, kan du endast använda en viss resultatgrupp för en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-250">Because a result group is related to the points that are associated with specific sets of questions on a questionnaire, you can use only a specific result group for a questionnaire.</span></span>

#### <a name="example-pointstexts-for-result-group-3"></a><span data-ttu-id="1b40f-251">Exempel: Poäng/texter för resultatgrupp 3</span><span class="sxs-lookup"><span data-stu-id="1b40f-251">Example: Points/texts for result group 3</span></span>

<span data-ttu-id="1b40f-252">Du använder en enkät för ett ledarskapstest som har 15 frågor i tre kategorier.</span><span class="sxs-lookup"><span data-stu-id="1b40f-252">You're using a questionnaire for a leadership test that has 15 questions in three categories.</span></span> <span data-ttu-id="1b40f-253">Du skapar tre resultatgrupper och lägger till fem frågor till varje resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="1b40f-253">You create three result groups and add five questions to each result group.</span></span> <span data-ttu-id="1b40f-254">Poängen räknas sedan samman i de tre grupperna.</span><span class="sxs-lookup"><span data-stu-id="1b40f-254">Points are then totaled in the three groups.</span></span> <span data-ttu-id="1b40f-255">De tre resultatgrupper är följande:</span><span class="sxs-lookup"><span data-stu-id="1b40f-255">The three result groups are as follows:</span></span>

-   <span data-ttu-id="1b40f-256">Kreativa förmågor</span><span class="sxs-lookup"><span data-stu-id="1b40f-256">Creative abilities</span></span>
-   <span data-ttu-id="1b40f-257">Ledarskapsförmågor</span><span class="sxs-lookup"><span data-stu-id="1b40f-257">Leadership abilities</span></span>
-   <span data-ttu-id="1b40f-258">Tekniska förmågor</span><span class="sxs-lookup"><span data-stu-id="1b40f-258">Technical abilities</span></span>

<span data-ttu-id="1b40f-259">Om du vill använda poängbaserade meddelanden, ställer du in textintervall för varje resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="1b40f-259">To use point-based messages, you set up text intervals for each result group.</span></span> <span data-ttu-id="1b40f-260">Varje fråga tilldelas två poäng.</span><span class="sxs-lookup"><span data-stu-id="1b40f-260">Each question is assigned two points.</span></span> <span data-ttu-id="1b40f-261">Därför är 10 den maximala poängsumman i varje resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="1b40f-261">Therefore, the maximum point total in each result group is 10.</span></span> 

<span data-ttu-id="1b40f-262">Följande tabell visar de poängbaserade meddelanden som du definierar i resultatgruppen "ledarskapsförmågor".</span><span class="sxs-lookup"><span data-stu-id="1b40f-262">The following table shows the point-based messages that you define for the “leadership abilities” result group.</span></span>

| <span data-ttu-id="1b40f-263">Poängintervall</span><span class="sxs-lookup"><span data-stu-id="1b40f-263">Point interval</span></span> | <span data-ttu-id="1b40f-264">Text</span><span class="sxs-lookup"><span data-stu-id="1b40f-264">Text</span></span>                                       |
|----------------|--------------------------------------------|
| <span data-ttu-id="1b40f-265">1 till 3</span><span class="sxs-lookup"><span data-stu-id="1b40f-265">1 to 3</span></span>         | <span data-ttu-id="1b40f-266">Du har genomsnittliga ledarskapförmågor.</span><span class="sxs-lookup"><span data-stu-id="1b40f-266">You have average leadership abilities.</span></span>     |
| <span data-ttu-id="1b40f-267">4 till 7</span><span class="sxs-lookup"><span data-stu-id="1b40f-267">4 to 7</span></span>         | <span data-ttu-id="1b40f-268">Du har goda ledarskapförmågor.</span><span class="sxs-lookup"><span data-stu-id="1b40f-268">You have good leadership abilities.</span></span>        |
| <span data-ttu-id="1b40f-269">8 till 10</span><span class="sxs-lookup"><span data-stu-id="1b40f-269">8 to 10</span></span>        | <span data-ttu-id="1b40f-270">Du har utmärkta ledarskapförmågor.</span><span class="sxs-lookup"><span data-stu-id="1b40f-270">You have outstanding leadership abilities.</span></span> |

<span data-ttu-id="1b40f-271">Du kan ställa in poängintervall och texter för varje resultatgrupp i en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-271">You can set up point intervals and texts for each result group on a questionnaire.</span></span> <span data-ttu-id="1b40f-272">Texter som motsvarar respektive svarandes poäng visas för varje resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="1b40f-272">Texts that correspond to each respondent’s score are displayed for each result group.</span></span> 

<span data-ttu-id="1b40f-273">**Anm.:** Du kan ändra intervall och texter.</span><span class="sxs-lookup"><span data-stu-id="1b40f-273">**Note:** You can change intervals and texts.</span></span> <span data-ttu-id="1b40f-274">Om en enkät har fyllts i kan dock ändringar orsaka skillnader mellan föregående och nya resultatrapporter.</span><span class="sxs-lookup"><span data-stu-id="1b40f-274">However, if a questionnaire has been completed, changes might cause differences between previous and new result reports.</span></span>

### <a name="conditional-question-hierarchies"></a><span data-ttu-id="1b40f-275">Hierarkier med villkorsfrågor</span><span class="sxs-lookup"><span data-stu-id="1b40f-275">Conditional question hierarchies</span></span>

<span data-ttu-id="1b40f-276">Hierarkier med villkorsfrågor är valfria när du skapar en enkät.</span><span class="sxs-lookup"><span data-stu-id="1b40f-276">Conditional question hierarchies are optional when you set up a questionnaire.</span></span> 

<span data-ttu-id="1b40f-277">**Anm.:** Innan du kan skapa en hierarki för villkorsfrågor måste du koppla frågor som har tilldelade svarsgrupper till enkäten.</span><span class="sxs-lookup"><span data-stu-id="1b40f-277">**Note:** Before you can set up a conditional question hierarchy, you must attach questions that have assigned answer groups to the questionnaire.</span></span> 

<span data-ttu-id="1b40f-278">Villkorsfrågor gör det möjligt att skapa en frågehierarki i en enkät och skapa en ordningsföljd för hur frågorna presenteras beroende på hur svaret den svarande valde för varje fråga.</span><span class="sxs-lookup"><span data-stu-id="1b40f-278">To use conditional questions to create a question hierarchy in a questionnaire, you can make the sequence that questions are presented in depend on the answer that a respondent selects for each question.</span></span> <span data-ttu-id="1b40f-279">Genom att på detta sätt basera frågesekvensen på svaren kan du ändra enkäten medan den svarande svarar på den.</span><span class="sxs-lookup"><span data-stu-id="1b40f-279">By basing the question sequence on a respondent’s answer, you can modify the questionnaire as the respondent completes it.</span></span>

#### <a name="examples"></a><span data-ttu-id="1b40f-280">Exempel</span><span class="sxs-lookup"><span data-stu-id="1b40f-280">Examples</span></span>

<span data-ttu-id="1b40f-281">En juridisk person erbjuder både artiklar och tjänster till dess kunder.</span><span class="sxs-lookup"><span data-stu-id="1b40f-281">A legal entity offers both items and services to its customers.</span></span> <span data-ttu-id="1b40f-282">Som inträffar normalt i sådana fall köper en del kunder endast artiklar, andra bara tjänster och en del köper både artiklar och tjänster.</span><span class="sxs-lookup"><span data-stu-id="1b40f-282">As typically occurs in such cases, some customers purchase only items, some purchase only services, and some purchase both items and services.</span></span> <span data-ttu-id="1b40f-283">Om företaget skickar ut en enkät om kundnöjdhet, använder det en villkorsstruktur i enkäten så att kunder som endast köper tjänster slipper att svara på frågor om artiklar.</span><span class="sxs-lookup"><span data-stu-id="1b40f-283">Therefore, when the legal entity distributes a customer satisfaction survey, it applies a conditional structure to the questionnaire, so that customers who purchase only services don't have to answer questions about items.</span></span> 

<span data-ttu-id="1b40f-284">Alternativt kan du skapa en enkät så att om den svarande väljer Svar A på fråga 1 är fråga 2 är nästa fråga i frågesekvensen.</span><span class="sxs-lookup"><span data-stu-id="1b40f-284">Alternatively, you set up a questionnaire so that if a respondent selects answer A for question 1, question 2 is next in the question sequence.</span></span> <span data-ttu-id="1b40f-285">Om svarande väljer svar B på fråga 1 följs den av fråga 5.</span><span class="sxs-lookup"><span data-stu-id="1b40f-285">However, if the respondent selects answer B for question 1, question 5 is next.</span></span>

<a name="see-also"></a><span data-ttu-id="1b40f-286">Se även</span><span class="sxs-lookup"><span data-stu-id="1b40f-286">See also</span></span>
--------

[<span data-ttu-id="1b40f-287">Använda enkäter</span><span class="sxs-lookup"><span data-stu-id="1b40f-287">Using questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="1b40f-288">Distribuera och slutföra enkäter</span><span class="sxs-lookup"><span data-stu-id="1b40f-288">Distributing and completing questionnaires</span></span>](distribute-questionnaires.md)

[<span data-ttu-id="1b40f-289">Visa och utvärdera resultaten av en enkät</span><span class="sxs-lookup"><span data-stu-id="1b40f-289">Viewing and evaluating the results of questionnaires</span></span>](evaluate-questionnaire-results.md)


