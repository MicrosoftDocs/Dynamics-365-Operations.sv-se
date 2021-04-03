---
title: Identifiera och lösa konflikter vid ansvarsfördelning
description: Det här avsnittet förklarar hur du identifierar och löser konflikter vid ansvarsfördelning.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: daf303a6bc3115363b27a6ebf7cc1832fdb6229d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5571039"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a><span data-ttu-id="58228-103">Identifiera och lösa konflikter vid ansvarsfördelning</span><span class="sxs-lookup"><span data-stu-id="58228-103">Identify and resolve conflicts in segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="58228-104">Det här avsnittet förklarar hur du identifierar och löser konflikter vid ansvarsfördelning.</span><span class="sxs-lookup"><span data-stu-id="58228-104">This topic explains how to identify and resolve conflicts in segregation of duties.</span></span> <span data-ttu-id="58228-105">Du kan ställa in regler för att separera uppgifter som måste utföras av andra användare.</span><span class="sxs-lookup"><span data-stu-id="58228-105">You can set up rules to separate duties that must be performed by different users.</span></span> <span data-ttu-id="58228-106">Detta koncept kallas ansvarsfördelning.</span><span class="sxs-lookup"><span data-stu-id="58228-106">This concept is named segregation of duties.</span></span> <span data-ttu-id="58228-107">När definitionen av en säkerhetsroll eller rolltilldelningarna av en användare bryter mot reglerna loggas konflikten.</span><span class="sxs-lookup"><span data-stu-id="58228-107">When the definition of a security role or the role assignments of a user violate the rules, the conflict is logged.</span></span> <span data-ttu-id="58228-108">Alla konflikter måste lösas av administratören.</span><span class="sxs-lookup"><span data-stu-id="58228-108">All conflicts must be resolved by the administrator.</span></span> <span data-ttu-id="58228-109">Slutför proceduren nedan för att identifiera och lösa konflikter.</span><span class="sxs-lookup"><span data-stu-id="58228-109">Complete the following procedure to identify and resolve conflicts.</span></span>

<span data-ttu-id="58228-110">När en regel har lagts till kontrollerar du att alla befintliga roller är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="58228-110">After a rule has been added, verify that all existing roles are compliant.</span></span> 

## <a name="verify-that-existing-roles-and-duties-comply-with-new-rules-for-segregation-of-duties"></a><span data-ttu-id="58228-111">Verifiera om befintliga roller och uppgifter följer de nya reglerna för ansvarsfördelning</span><span class="sxs-lookup"><span data-stu-id="58228-111">Verify that existing roles and duties comply with new rules for segregation of duties</span></span>
1. <span data-ttu-id="58228-112">Gå till **Systemadministration** > **Säkerhet** > **Ansvarsfördelning** > **Ansvarsfördelningsregler**.</span><span class="sxs-lookup"><span data-stu-id="58228-112">Go to **System administration** > **Security** > **Segregation of duties** > **Segregation of duties rules**.</span></span>
3. <span data-ttu-id="58228-113">Välj **Validera programbehörigheter och roller**.</span><span class="sxs-lookup"><span data-stu-id="58228-113">Select **Validate duties and roles**.</span></span> <span data-ttu-id="58228-114">Om några roller strider mot reglerna visas ett meddelande som innehåller namnet på rollen, rollen och namnen på de motstridiga uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="58228-114">If any roles violate the rules, a message is displayed that contains the name of the rule, the role, and the names of the conflicting duties.</span></span> <span data-ttu-id="58228-115">Konfliktroller måste ändras med hjälp av **Säkerhetskonfiguration** och kan inte inkludera motstridiga uppgifter.</span><span class="sxs-lookup"><span data-stu-id="58228-115">Conflicting roles must be modified using **Security configuration** and can't include conflicting duties.</span></span> <span data-ttu-id="58228-116">Om inga roller strider mot den valda regeln visas ett meddelande om att alla roller efterlevs.</span><span class="sxs-lookup"><span data-stu-id="58228-116">If no roles violate the selected rule, a message indicates that all roles comply.</span></span>   

> [!NOTE]
> <span data-ttu-id="58228-117">Verifieringen utförs endast för den valda regeln.</span><span class="sxs-lookup"><span data-stu-id="58228-117">The validation is only performed for the selected rule.</span></span> <span data-ttu-id="58228-118">Det är viktigt att validera efterlevnad för varje regel.</span><span class="sxs-lookup"><span data-stu-id="58228-118">It is important to validate compliance for each rule.</span></span>   

<span data-ttu-id="58228-119">När du skapar eller ändrar en roll, verkställs automatiskt reglerna för ansvarsfördelning.</span><span class="sxs-lookup"><span data-stu-id="58228-119">When you create or modify a role, the rules for segregation of duties are automatically enforced.</span></span> <span data-ttu-id="58228-120">Du kan inte tilldela en roll motstridiga uppgifter.</span><span class="sxs-lookup"><span data-stu-id="58228-120">You cannot assign conflicting duties to a role.</span></span>

<span data-ttu-id="58228-121">Kontrollera sedan att alla befintliga rolltilldelningar är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="58228-121">Next, verify that all existing role assignments are compliant.</span></span>

## <a name="verify-that-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a><span data-ttu-id="58228-122">Verifiera att användarrolltilldelningar följer de nya reglerna för ansvarsfördelning</span><span class="sxs-lookup"><span data-stu-id="58228-122">Verify that user role assignments comply with new rules for segregation of duties</span></span>
1. <span data-ttu-id="58228-123">Gå till **Systemadministration > Säkerhet > Ansvarsfördelning > Verifiera regelefterlevnad för användarrolltilldelningar**.</span><span class="sxs-lookup"><span data-stu-id="58228-123">Go to **System administration > Security > Segregation of duties > Verify compliance of user-role assignments**.</span></span>
2. <span data-ttu-id="58228-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="58228-124">Select **OK**.</span></span> <span data-ttu-id="58228-125">Ett meddelande visar resultaten för valideringen.</span><span class="sxs-lookup"><span data-stu-id="58228-125">A notification displays the results of the validation.</span></span> <span data-ttu-id="58228-126">Konflikter loggas på sidan **Olösta ansvarsfördelningskonflikter**.</span><span class="sxs-lookup"><span data-stu-id="58228-126">Conflicts are logged on the **Segregation of duties unresolved conflicts** page.</span></span>   

<span data-ttu-id="58228-127">När du skapar eller tilldelar användare till en roll, verkställs automatiskt reglerna för ansvarsfördelning.</span><span class="sxs-lookup"><span data-stu-id="58228-127">When you assign users to roles, the rules for segregation of duties are automatically enforced.</span></span> <span data-ttu-id="58228-128">Om du försöker tilldela en användare till roller som innehåller motstridiga uppgifter visas ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="58228-128">If you try to assign a user to roles that contain conflicting duties, you receive an error message.</span></span> <span data-ttu-id="58228-129">Du måste sedan lösa konflikten genom att neka eller tillåta den ytterligare rolltilldelningen.</span><span class="sxs-lookup"><span data-stu-id="58228-129">You must then resolve the conflict by denying or allowing the additional role assignment.</span></span> <span data-ttu-id="58228-130">Den ytterligare rollen kommer att tilldelas efter tilldelningen är tillåten.</span><span class="sxs-lookup"><span data-stu-id="58228-130">The additional role will be assigned after the assignment is allowed.</span></span> 

> [!NOTE]
> <span data-ttu-id="58228-131">Konflikter verifieras för närvarande inte för användare som är tilldelade roller baserat på Active Directory Domain-grupperna.</span><span class="sxs-lookup"><span data-stu-id="58228-131">Conflicts are currently not verified for users that are assigned roles based on the Active Directory Domain groups.</span></span>

## <a name="view-and-resolve-conflicting-user-role-assignments"></a><span data-ttu-id="58228-132">Visa och lös motstridiga tilldelningar av användarroller</span><span class="sxs-lookup"><span data-stu-id="58228-132">View and resolve conflicting user role assignments</span></span>
1. <span data-ttu-id="58228-133">Gå till **Systemadministration** > **Säkerhet** > **Ansvarsfördelning** > **Olösta ansvarsfördelningskonflikter**.</span><span class="sxs-lookup"><span data-stu-id="58228-133">Go to **System administration** > **Security** > **Segregation of duties** > **Segregation of duties unresolved conflicts**.</span></span> 
2. <span data-ttu-id="58228-134">Markera en konflikt och klicka sedan på någon av följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="58228-134">Select a conflict, and then select one of the following actions:</span></span> 

  - <span data-ttu-id="58228-135">**Neka tilldelning**: Detta nekar tilldelningen av användaren i den ytterligare säkerhetsrollen.</span><span class="sxs-lookup"><span data-stu-id="58228-135">**Deny assignment**: This will deny the assignment of the user to the additional security role.</span></span> <span data-ttu-id="58228-136">Om du nekar en automatisk rolltilldelning markeras användaren som utesluten från rollen.</span><span class="sxs-lookup"><span data-stu-id="58228-136">If you deny an automatic role assignment, the user is marked as excluded from the role.</span></span> <span data-ttu-id="58228-137">Den uteslutna användaren beviljas inte åtkomsten som associeras med rollen och användaren kan inte tilldelas rollen tills administratören tar bort uteslutandet.</span><span class="sxs-lookup"><span data-stu-id="58228-137">The excluded user isn't granted the access associated with the role and can't be assigned to the role until the administrator removes the exclusion.</span></span> 
-  <span data-ttu-id="58228-138">**Tillåt tilldelning**: Detta åsidosätter konflikten och tillåt användaren tilldelas den ytterligare säkerhetsrollen.</span><span class="sxs-lookup"><span data-stu-id="58228-138">**Allow assignment**: This will override the conflict and allow the user to be assigned to the additional security role.</span></span> <span data-ttu-id="58228-139">Om du åsidosätter en konflikt måste du ange en orsak i fältet **Orsak till åsidosättning**.</span><span class="sxs-lookup"><span data-stu-id="58228-139">If you override a conflict, you must enter a reason in the **Reason for override** field.</span></span> <span data-ttu-id="58228-140">Alla åsidosatta rolltilldelningar kan visas på sidan **Ansvarsfördelningskonflikter**.</span><span class="sxs-lookup"><span data-stu-id="58228-140">All overridden role assignments can be viewed on the **Segregation of duties conflicts** page.</span></span>  

> [!NOTE]
> <span data-ttu-id="58228-141">Om flera konflikter finns med för samma användare väljer du användarposten och utvärderar tilldelade roller på sidan **Användare**.</span><span class="sxs-lookup"><span data-stu-id="58228-141">If several conflicts are listed for the same user, select the user record and evaluate assigned roles on the **Users** page.</span></span> <span data-ttu-id="58228-142">Undvik den här konflikten genom att validera varje regel när den har lagts till eller ändrats.</span><span class="sxs-lookup"><span data-stu-id="58228-142">To avoid this conflict, validate each rule after it's added or modified.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]