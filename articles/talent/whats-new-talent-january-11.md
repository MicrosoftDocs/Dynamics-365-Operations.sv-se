---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (11 januari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
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
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d49a4aca368e3de10ae37b56c6d286d78f7f369a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899184"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-11-2019"></a><span data-ttu-id="71ab8-103">Nyheter och ändringar i Dynamics 365 Talent - Core HR (11 januari 2019)</span><span class="sxs-lookup"><span data-stu-id="71ab8-103">What's new or changed in Dynamics 365 Talent - Core HR (January 11, 2019)</span></span>

<span data-ttu-id="71ab8-104">**Skapa 8.1.2100**</span><span class="sxs-lookup"><span data-stu-id="71ab8-104">**Build 8.1.2100**</span></span>

<span data-ttu-id="71ab8-105">Det här ämnet beskriver nya eller ändrade funktioner i Core HR.</span><span class="sxs-lookup"><span data-stu-id="71ab8-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="71ab8-106">Ändringar</span><span class="sxs-lookup"><span data-stu-id="71ab8-106">Changes</span></span>

### <a name="validate-leave-requests-by-forecasting-available-balance"></a><span data-ttu-id="71ab8-107">Validera ledighetsansökningar genom prognoser tillgängligt saldo</span><span class="sxs-lookup"><span data-stu-id="71ab8-107">Validate leave requests by forecasting available balance</span></span>
<span data-ttu-id="71ab8-108">Ändringar i den här versionen tillåter medarbetare att begära framtida ledighet utan att man subtraherar från deras aktuella saldo.</span><span class="sxs-lookup"><span data-stu-id="71ab8-108">Changes made in this release allow employees to request future leave time without subtracting from their current balance.</span></span> <span data-ttu-id="71ab8-109">Standardarbetsflöden används för alla framtida begäran.</span><span class="sxs-lookup"><span data-stu-id="71ab8-109">Standard workflows will be used for any future requests made.</span></span> <span data-ttu-id="71ab8-110">Mer information finns i [periodisering av timmar baserat på arbetstid](leave-accrue-hours-worked.md).</span><span class="sxs-lookup"><span data-stu-id="71ab8-110">For more information, read [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a><span data-ttu-id="71ab8-111">Visa prognostiserat ledighetssaldo i ESS och Användare</span><span class="sxs-lookup"><span data-stu-id="71ab8-111">View forecasted leave balance in ESS and People</span></span>
<span data-ttu-id="71ab8-112">Den här funktionen låter dig visa saldon för framtida ledighetsperioder av personal, chefer och medarbetare.</span><span class="sxs-lookup"><span data-stu-id="71ab8-112">This feature enables viewing of balances for future leave periods by HR, managers, and employees.</span></span> <span data-ttu-id="71ab8-113">Medarbetare kan visa framtida saldon i arbetsytan **Självbetjäning för medarbetare** och personal har tillgång till samma information med arbetsytan **Användare**.</span><span class="sxs-lookup"><span data-stu-id="71ab8-113">Employees can view future balances in the **Employee Self-Service** workspace and HR has access to the same information using the **People** workspace.</span></span>

### <a name="notifications-for-changing-leave-balances"></a><span data-ttu-id="71ab8-114">Meddelanden för att ändra ledighetssaldon</span><span class="sxs-lookup"><span data-stu-id="71ab8-114">Notifications for changing leave balances</span></span>
<span data-ttu-id="71ab8-115">Ledighetssaldon visar det aktuella saldot för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="71ab8-115">Leave balances will display the employees current balance.</span></span> <span data-ttu-id="71ab8-116">Det finns framtida saldon på arbetsytorna **Självbetjäning för medarbetare** och **Användare** genom att ange ”från och med datum” för att beräkna prognostiserade saldot.</span><span class="sxs-lookup"><span data-stu-id="71ab8-116">Future balances are available on the **Employee Self-Service** and **People** workspaces by entering an “as of date” to calculate the forecasted balance.</span></span>

<span data-ttu-id="71ab8-117">Navigering har lagts till för att visa förväntade saldon i följande områden:</span><span class="sxs-lookup"><span data-stu-id="71ab8-117">Navigation has been added to view forecasted balances in the following areas:</span></span>
  - <span data-ttu-id="71ab8-118">Kortet **Ledighet** på arbetsytan **Självbetjäning för medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="71ab8-118">**Time off** card on the **Employee Self-Service** workspace.</span></span>
  - <span data-ttu-id="71ab8-119">Kortet **Ledighet och frånvaro** på arbetsytan **Självbetjäning för chef**.</span><span class="sxs-lookup"><span data-stu-id="71ab8-119">**Leave and absence** card on the **Manager Self-Service** workspace.</span></span>
  - <span data-ttu-id="71ab8-120">Sidan **Ledighet och frånvaro** på arbetsytan **Användare**.</span><span class="sxs-lookup"><span data-stu-id="71ab8-120">**Leave and absence** page on the **People** workspace.</span></span>

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a><span data-ttu-id="71ab8-121">Tillåt decimaler för variabla kompensationsplaner (kontantplaner)</span><span class="sxs-lookup"><span data-stu-id="71ab8-121">Allow decimals for Variable compensation plans (Cash plans)</span></span>
<span data-ttu-id="71ab8-122">Variabel kontant ersättning och planer har nu ytterligare flexibilitet för belopp och åsidosätter värden med decimala belopp.</span><span class="sxs-lookup"><span data-stu-id="71ab8-122">Variable cash awards and plans now have the additional flexibility for amounts and overrides for values with decimal amounts.</span></span>

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a><span data-ttu-id="71ab8-123">Det går inte att ändra datumen på registreringar av variabel kompensation när planen har sparats</span><span class="sxs-lookup"><span data-stu-id="71ab8-123">Unable to change the dates on Variable comp enrollments after the plan is saved</span></span>
<span data-ttu-id="71ab8-124">Denna ändring gör att slutdatumet för planen uppdateras (utökad eller utgången) när planen har sparats.</span><span class="sxs-lookup"><span data-stu-id="71ab8-124">This change allows for the plan end date to be updated (extended or expired) after the plan has been saved.</span></span> <span data-ttu-id="71ab8-125">Du kan fortfarande aktivera eller inaktivera planer oberoende av start- och slutdatumen.</span><span class="sxs-lookup"><span data-stu-id="71ab8-125">You can still activate or de-activate plans independent of start and end dates.</span></span>

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a><span data-ttu-id="71ab8-126">Löneinformation som är tillgänglig när säkerhetsrollen Löneadministratör tilldelats</span><span class="sxs-lookup"><span data-stu-id="71ab8-126">Payroll information available when assigned the Payroll admin security role</span></span>
<span data-ttu-id="71ab8-127">Löneadministratörsrollen har uppdaterats för att komma åt löneinformation under förfråganprocessen.</span><span class="sxs-lookup"><span data-stu-id="71ab8-127">The Payroll Administrator role has been updated to have access to the payroll information during the request process.</span></span>

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="71ab8-128">Självservice för anställda | nedrullningsmenyn för befattningshierarkin från panel misslyckas med att hämta överordnad nod</span><span class="sxs-lookup"><span data-stu-id="71ab8-128">Employee self-service | Position hierarchy drill-down from tile fails to get parent node</span></span>
<span data-ttu-id="71ab8-129">Ändringar har gjorts för att ta bort ett fel som uppstod när du lägger till befattningshierarkin till nya arbetsytor och navigerar i organisationsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="71ab8-129">Changes have been made to eliminate an error that occurred when adding the position hierarchy to new workspaces and navigating within the organizational structure.</span></span>

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a><span data-ttu-id="71ab8-130">Nytt verifieringsmeddelande när personalnummerserien används</span><span class="sxs-lookup"><span data-stu-id="71ab8-130">New validation message when personnel number sequence is in use</span></span>
<span data-ttu-id="71ab8-131">En ändring har gjorts för att klargöra vad problemet är när du anställer en medarbetare och nästa personalnumret används.</span><span class="sxs-lookup"><span data-stu-id="71ab8-131">A change has been made to clarify what the issue is when you hire an employee and the next personnel number is in use.</span></span>

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a><span data-ttu-id="71ab8-132">Arbetsytan för medarbetarens självbetjäning har valts som den ursprungliga startsidan</span><span class="sxs-lookup"><span data-stu-id="71ab8-132">Employee self-service workspace selected as the initial startup page</span></span>
<span data-ttu-id="71ab8-133">När arbetsytan **medarbetarens självbetjäning** är markerad som den ursprungliga startsidan för en användare, och användaren inte är tilldelad medarbetarrollen kan systemet dirigeras till standardinstrumentpanel.</span><span class="sxs-lookup"><span data-stu-id="71ab8-133">When the **Employee self-service** workspace is selected as the initial startup page for a user and that user is not assigned the employee role, the system will redirect to the default dashboard.</span></span>

### <a name="termination-reason-code-updates-position-assignment-record"></a><span data-ttu-id="71ab8-134">Orsakskod till uppsägningen uppdaterar befattningstilldelningsposten</span><span class="sxs-lookup"><span data-stu-id="71ab8-134">Termination reason code updates position assignment record</span></span>
<span data-ttu-id="71ab8-135">Orsakskoden till uppsägning uppdaterar nu befattningstilldelningen när du säger upp en medarbetare och avslutar befattningen.</span><span class="sxs-lookup"><span data-stu-id="71ab8-135">The termination reason code will now update the position assignment when terminating an employee and ending the position.</span></span> 
