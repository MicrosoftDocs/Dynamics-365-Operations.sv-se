---
title: Integration för serviceavtal och projekt
description: När du arbetar med serviceavtal och serviceavtalsrader, använder du data som konfigurerats i följande områden av avsnittet Projekthantering och redovisning.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6bd2fb1f54a3decb77f019db6b2016cebdcaddb9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571059"
---
# <a name="integration-for-service-agreements-and-projects"></a><span data-ttu-id="5afac-103">Integration för serviceavtal och projekt</span><span class="sxs-lookup"><span data-stu-id="5afac-103">Integration for service agreements and projects</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="5afac-104">När du arbetar med serviceavtal och serviceavtalsrader, använder du data som konfigurerats i följande områden i **Projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="5afac-104">When you work with service agreements and service agreement lines, you use data that is set up in the following areas in **Project management and accounting**.</span></span>

## <a name="project-prices"></a><span data-ttu-id="5afac-105">Projektpriser</span><span class="sxs-lookup"><span data-stu-id="5afac-105">Project prices</span></span>

<span data-ttu-id="5afac-106">Kostnaden och försäljningspriset för en serviceavtalstransaktion härleds från den inställning av självkostnad som gäller för projektet som är kopplat till serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="5afac-106">The cost and the sales price for a service agreement transaction are derived from the cost price setup that applies to the project that is attached to the service agreement.</span></span> <span data-ttu-id="5afac-107">Kostnad och försäljningspris kan konfigureras per projekt, medarbetare och kategori.</span><span class="sxs-lookup"><span data-stu-id="5afac-107">Cost and sales prices can be set up by project, employee, and category.</span></span> 

## <a name="project-validation"></a><span data-ttu-id="5afac-108">Projektvalidering</span><span class="sxs-lookup"><span data-stu-id="5afac-108">Project validation</span></span>

<span data-ttu-id="5afac-109">De projekt, medarbetare och kategorier som är tillgängliga för urval på en serviceavtalsrad kan begränsas via valideringskonfigureringen i **Projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="5afac-109">The projects, employees, and categories that are available for selection on a service agreement line can be limited by the validation setup in **Project management and accounting**.</span></span> <span data-ttu-id="5afac-110">Med valideringskonfigureringen kan du kombinera medarbetare, projekt och kategorier och därigenom styra åtkomsten.</span><span class="sxs-lookup"><span data-stu-id="5afac-110">By using the validation setup, you can combine employees, projects, and categories for control access.</span></span> 

## <a name="project-line-properties"></a><span data-ttu-id="5afac-111">Radegenskaper för projekt</span><span class="sxs-lookup"><span data-stu-id="5afac-111">Project line properties</span></span>

<span data-ttu-id="5afac-112">En radegenskap registreras automatiskt för en serviceavtalsrad.</span><span class="sxs-lookup"><span data-stu-id="5afac-112">A line property is entered automatically for a service agreement line.</span></span>

<span data-ttu-id="5afac-113">Radegenskaper skapas i formuläret **Radegenskaper** i **projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="5afac-113">Line properties are created in the **Line properties** form in **Project management and accounting**.</span></span> <span data-ttu-id="5afac-114">Den radegenskap som registreras i ett serviceavtal kopplas till det projekt som valts för serviceavtalet och senare ärvs av serviceavtalsraden.</span><span class="sxs-lookup"><span data-stu-id="5afac-114">The line property that is entered on a service agreement is attached to the project that is selected for the service agreement and inherited subsequently by the service agreement line.</span></span> 

## <a name="default-offset-accounts"></a><span data-ttu-id="5afac-115">Standardmotkonton</span><span class="sxs-lookup"><span data-stu-id="5afac-115">Default offset accounts</span></span>

<span data-ttu-id="5afac-116">Om du anger en utgiftstransaktion markeras ett standardmotkonto automatiskt för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="5afac-116">If you enter an expense transaction, a default expense offset account is selected automatically for the transaction.</span></span> <span data-ttu-id="5afac-117">Standardmotkontot konfigureras i projektet som är kopplat till det aktuella serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="5afac-117">The default expense account is set up for the project that is attached to the current service agreement.</span></span>

## <a name="project-categories"></a><span data-ttu-id="5afac-118">Projektkategorier</span><span class="sxs-lookup"><span data-stu-id="5afac-118">Project categories</span></span>

<span data-ttu-id="5afac-119">De kategorier som är tillgängliga för serviceavtalsrader konfigureras i formuläret **Projektkategorier** i **Projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="5afac-119">The categories that are available for service agreement lines are set up in the **Project categories** form in **Project management and accounting**.</span></span> 

> [!NOTE]
> <P><span data-ttu-id="5afac-120">Kategorier som har kryssrutan <STRONG>Aktiv i journaler</STRONG> markerad på fliken <STRONG>projekt</STRONG> i formuläret <STRONG>projektkategorier</STRONG> kan väljas.</span><span class="sxs-lookup"><span data-stu-id="5afac-120">Categories that have the <STRONG>Active in journals</STRONG> check box selected on the <STRONG>Project</STRONG> tab in the <STRONG>Project categories</STRONG> form are available for selection.</span></span> <span data-ttu-id="5afac-121">Men om kryssrutan <STRONG>inaktiva kategorier</STRONG> är markerad på fliken <STRONG>journaler</STRONG> i formuläret <STRONG>projekthantering och redovisningsparametrar</STRONG> kan alla kategorier kan väljas.</span><span class="sxs-lookup"><span data-stu-id="5afac-121">However, if the <STRONG>Inactive categories</STRONG> check box is selected on the <STRONG>Journals</STRONG> tab in the <STRONG>Project management and accounting parameters</STRONG> form, all categories are available for selection.</span></span></P>

## <a name="project-parameters"></a><span data-ttu-id="5afac-122">Projektparametrar</span><span class="sxs-lookup"><span data-stu-id="5afac-122">Project parameters</span></span>

<span data-ttu-id="5afac-123">Om fältet **avslutade arbetare** på fliken **journaler** i formuläret **projekthantering och redovisningsparametrar** markeras kan du välja inaktiva medarbetare och aktiva medarbetare i formuläret **Serviceavtal** och **serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="5afac-123">If the **Terminated workers** field on the **Journals** tab in the **Project management and accounting parameters** form is selected, you can select inactive employees and active employees in the **Service agreements** and **Service orders** forms.</span></span>

<span data-ttu-id="5afac-124">Du kan även aktivera fälten **Starttid** och **Sluttid** på fliken **Projekt** i formuläret **Serviceorder** för att ange start- och sluttider på serviceorderrader.</span><span class="sxs-lookup"><span data-stu-id="5afac-124">Also, you can enable the **Start time** and **End time** fields on the **Project** tab in the **Service orders** form to enter starting and ending times on service order lines.</span></span>

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a><span data-ttu-id="5afac-125">Aktivera funktionen för start- och sluttid för serviceorder</span><span class="sxs-lookup"><span data-stu-id="5afac-125">Enable the starting and ending time feature for service orders</span></span>

1.  <span data-ttu-id="5afac-126">Klicka på **Projekthantering och redovisning** \> **Inställningar** \> **Parametrar för projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="5afac-126">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="5afac-127">Klicka på fliken **journaler** och markera sedan kryssrutan **Visa start-/ sluttider**.</span><span class="sxs-lookup"><span data-stu-id="5afac-127">Click the **Journals** tab, and then select the **Show start/end times** check box.</span></span>

3.  <span data-ttu-id="5afac-128">Klicka på **Projekthantering och redovisning** \> **Inställning** \> **Journaler** \> **Journalnamn**.</span><span class="sxs-lookup"><span data-stu-id="5afac-128">Click **Project management and accounting** \> **Setup** \> **Journals** \> **Journal names**.</span></span>

4.  <span data-ttu-id="5afac-129">Markera journalnamnet som är kopplat till serviceordern.</span><span class="sxs-lookup"><span data-stu-id="5afac-129">Select the journal name that is attached to the service order.</span></span>

5.  <span data-ttu-id="5afac-130">Klicka på fliken **Allmänt** och markera sedan kryssrutan **Visa start-/ sluttider**.</span><span class="sxs-lookup"><span data-stu-id="5afac-130">Click the **General** tab, and then select the **Show start/end times** check box.</span></span>


> [!NOTE]
> <P><span data-ttu-id="5afac-131">Markera journalnamnet för serviceordern i fältet <STRONG>timme</STRONG> på fliken <STRONG>journaler</STRONG> i formuläret <STRONG>Serviceparametrar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5afac-131">Select the journal name for the service order in the <STRONG>Hour</STRONG> field on the <STRONG>Journals</STRONG> tab in the <STRONG>Service management parameters</STRONG> form.</span></span></P>





