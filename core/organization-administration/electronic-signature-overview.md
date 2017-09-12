---
title: "Översikt över elektroniska signaturer"
description: "Den här artikeln innehåller en översikt över elektroniska signaturer samt en beskrivning av hur de kan användas i Microsoft Dynamics 365 for Finance and Operations."
author: maertenm
manager: AnnBe
ms.date: 08/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e81d4a29cf1624619c1f0c2bfc6bc66c715a6b7f
ms.openlocfilehash: fa3aff17f3f55cdee9abf1f0326ac2bbe599bf94
ms.contentlocale: sv-se
ms.lasthandoff: 08/24/2017

---

# <a name="electronic-signature-overview"></a><span data-ttu-id="44582-103">Översikt över elektroniska signaturer</span><span class="sxs-lookup"><span data-stu-id="44582-103">Electronic signature overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="44582-104">Den här artikeln innehåller en översikt över elektroniska signaturer samt en beskrivning av hur de kan användas i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="44582-104">This article provides an overview of electronic signatures and describes how they can be used in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<a name="what-is-an-electronic-signature"></a><span data-ttu-id="44582-105">Vad är en elektronisk signatur?</span><span class="sxs-lookup"><span data-stu-id="44582-105">What is an electronic signature?</span></span>
--------------------------------

<span data-ttu-id="44582-106">En elektronisk signatur bekräftar identiteten hos en person som ska påbörja eller godkänna en dataprocess.</span><span class="sxs-lookup"><span data-stu-id="44582-106">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="44582-107">I vissa branscher är en elektronisk signatur lika juridiskt bindande som en handskriven signatur.</span><span class="sxs-lookup"><span data-stu-id="44582-107">In some industries, an electronic signature is as legally binding as a handwritten signature.</span></span> 

<span data-ttu-id="44582-108">Elektroniska signaturer är ett juridiskt krav för flera reglerade branscher som läkemedelsbranschen, livsmedelsbranschen, samt rymd- och försvarsbranschen.</span><span class="sxs-lookup"><span data-stu-id="44582-108">Electronic signatures are a regulations compliance requirement for several regulated industries, such as pharmaceuticals, food and beverage, and aerospace and defense.</span></span> <span data-ttu-id="44582-109">De krävs även för att överensstämma med reglerna i 21 CFR del 11 som utfärdades av Food and Drug Administration (FDA) i USA.</span><span class="sxs-lookup"><span data-stu-id="44582-109">They are also required for compliance with regulations in 21 CFR Part 11 that was issued by the Food and Drug Administration (FDA) in the United States.</span></span> 

<span data-ttu-id="44582-110">**Obs!** En elektronisk signatur är i sig inte detsamma som en digital signatur.</span><span class="sxs-lookup"><span data-stu-id="44582-110">**Note:** An electronic signature by itself isn't the same as a digital signature.</span></span> <span data-ttu-id="44582-111">En elektronisk signatur ersätter helt enkelt en handskriven signatur, medan en digital signatur innehåller ytterligare säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="44582-111">An electronic signature is just a substitute for a handwritten signature, whereas a digital signature provides additional security measures.</span></span> <span data-ttu-id="44582-112">Med en digital signatur kan det vara möjligt att identifiera om en annan användare eller process har manipulerat data.</span><span class="sxs-lookup"><span data-stu-id="44582-112">A digital signature can help identify whether another user or process has tampered with the data.</span></span> <span data-ttu-id="44582-113">En digital signatur kan även verifieras och denna verifiering kan inte tillbakavisas av ägaren av certifikatet som användes för att signera data.</span><span class="sxs-lookup"><span data-stu-id="44582-113">A digital signature can also be verified, and this verification can't be refuted by the owner of the certificate that was used to sign the data.</span></span> <span data-ttu-id="44582-114">Som beskrivs nedan har elektroniska signaturer i Microsoft Dynamics 365 for Finance and Operations en inbyggd funktion för digital signatur.</span><span class="sxs-lookup"><span data-stu-id="44582-114">As described below, electronic signatures in Microsoft Dynamics 365 for Finance and Operations have built-in digital signature functionality.</span></span>

## <a name="electronic-signatures-in-dynamics-365-for-finance-and-operations"></a><span data-ttu-id="44582-115">Elektroniska signaturer i Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="44582-115">Electronic signatures in Dynamics 365 for Finance and Operations</span></span>
<span data-ttu-id="44582-116">I Finance and Operations kan du använda elektroniska signaturer för kritiska affärsprocesser.</span><span class="sxs-lookup"><span data-stu-id="44582-116">In Finance and Operations, you can use electronic signatures for critical business processes.</span></span> <span data-ttu-id="44582-117">Vissa processer har inbyggda funktioner för elektronisk signatur.</span><span class="sxs-lookup"><span data-stu-id="44582-117">Some processes have built-in electronic signature capabilities.</span></span> <span data-ttu-id="44582-118">Du kan även skapa anpassade signaturkrav för alla databastabeller och fält.</span><span class="sxs-lookup"><span data-stu-id="44582-118">You can also create custom signature requirements for any database table and field.</span></span> 

<span data-ttu-id="44582-119">Elektroniska signaturer har en inbyggd funktion för digital signatur.</span><span class="sxs-lookup"><span data-stu-id="44582-119">Electronic signatures have built-in digital signature functionality.</span></span> <span data-ttu-id="44582-120">Alla användare som signerar dokument måste få ett giltigt kryptografiskt certifikat.</span><span class="sxs-lookup"><span data-stu-id="44582-120">Every user who signs documents must obtain a valid cryptographic certificate.</span></span> <span data-ttu-id="44582-121">När ett dokument signeras verifieras den privata nyckeln som är associerad med certifikatet.</span><span class="sxs-lookup"><span data-stu-id="44582-121">When a document is signed, the private key that is associated with that certificate is validated.</span></span> <span data-ttu-id="44582-122">Finance and Operations registrerar information om elektroniska signaturer i en logg för att tillhandahålla ett redovisningsspår.</span><span class="sxs-lookup"><span data-stu-id="44582-122">Finance and Operations records electronic signature information in a log to provide an audit trail.</span></span> <span data-ttu-id="44582-123">För att ställa in elektroniska signaturer, se [Ställ in elektroniska signaturer (uppgiftsguide)](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-up-electronic-signatures).</span><span class="sxs-lookup"><span data-stu-id="44582-123">To set up electronic signatures, see [Set up electronic signatures (Task guide)](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-up-electronic-signatures).</span></span>

## <a name="users-who-require-access-to-electronic-signatures"></a><span data-ttu-id="44582-124">Användare som behöver åtkomst till elektroniska signaturer</span><span class="sxs-lookup"><span data-stu-id="44582-124">Users who require access to electronic signatures</span></span>
<span data-ttu-id="44582-125">Tre typer av användare kräver normalt säkerhetsåtkomst till elektroniska signaturer: elektronisk signaturadministratörer, undertecknare och elektronisk signaturrevisorer.</span><span class="sxs-lookup"><span data-stu-id="44582-125">Three kinds of users typically require security access to electronic signatures: electronic signature administrators, signers, and electronic signature auditors.</span></span>

### <a name="electronic-signature-administrator"></a><span data-ttu-id="44582-126">Administratör för elektronisk signatur</span><span class="sxs-lookup"><span data-stu-id="44582-126">Electronic signature administrator</span></span>

<span data-ttu-id="44582-127">Administratören för elektronisk signatur konfigurerar signaturkrav, allmänna parametrar och godkännare samt tar emot aviseringar när signaturverifieringen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="44582-127">The electronic signature administrator sets up signature requirements, general parameters, and approvers, and receives alerts when signatures can't be verified.</span></span> <span data-ttu-id="44582-128">Som standard har en användare som tillhör säkerhetsrollen **IT-chef**, behörighet att administrera elektroniska signaturer.</span><span class="sxs-lookup"><span data-stu-id="44582-128">By default, a user who belongs to the **Information technology manager** security role has permission to administer electronic signatures.</span></span>

### <a name="signer"></a><span data-ttu-id="44582-129">Undertecknare</span><span class="sxs-lookup"><span data-stu-id="44582-129">Signer</span></span>

<span data-ttu-id="44582-130">En undertecknare tillhandahåller elektroniska signaturer för dokument och processer som kräver signaturer.</span><span class="sxs-lookup"><span data-stu-id="44582-130">A signer provides electronic signatures for documents and processes that require signatures.</span></span> <span data-ttu-id="44582-131">Som standard har en användare som tillhör **Systemanvändare** säkerhetsrollen, behörighet att signera dokument elektroniskt.</span><span class="sxs-lookup"><span data-stu-id="44582-131">By default, a user who belongs to the **System user** security role has permission to sign documents electronically.</span></span> 

<span data-ttu-id="44582-132">**Obs!** Undertecknaren kan behöva ytterligare behörigheter innan åtkomst beviljas till de data som rör dokumentet eller processen som signeras.</span><span class="sxs-lookup"><span data-stu-id="44582-132">**Note:** The signer might require additional permissions before access is granted to data that is related to the document or process that is being signed.</span></span> <span data-ttu-id="44582-133">En användare som ändrar data och sedan måste signera ändringarna måste ha behörighet att ändra data.</span><span class="sxs-lookup"><span data-stu-id="44582-133">A user who changes data and must then sign for those changes must have permission to change the data.</span></span> <span data-ttu-id="44582-134">En användare som signerar på uppdrag av en annan användare behöver eventuellt inte ha åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="44582-134">A user who signs on behalf of another user might not require access to the data.</span></span> <span data-ttu-id="44582-135">Ett exempel på den här typen av användaren är en arbetsledare som signerar en medarbetares ändringar.</span><span class="sxs-lookup"><span data-stu-id="44582-135">An example of this kind of user is a supervisor who signs for an employee's changes.</span></span>

### <a name="electronic-signature-auditor"></a><span data-ttu-id="44582-136">Revisor för elektronisk signatur</span><span class="sxs-lookup"><span data-stu-id="44582-136">Electronic signature auditor</span></span>

<span data-ttu-id="44582-137">Revisorn för elektronisk signatur granskar databasloggen och den signaturgranskningslogg som finns i databasloggen.</span><span class="sxs-lookup"><span data-stu-id="44582-137">The electronic signature auditor reviews the database log and the signature review log that is available from the database log.</span></span> <span data-ttu-id="44582-138">Som standard har en användare som tillhör säkerhetsrollen **IT-chef**, behörighet att granska elektroniska signaturer.</span><span class="sxs-lookup"><span data-stu-id="44582-138">By default, a user who belongs to the **Information technology manager** security role has permission to audit electronic signatures.</span></span> 

<span data-ttu-id="44582-139">Om du använder en annan roll än **IT-chef**, se till att tilldelas rollen följande behörigheter:</span><span class="sxs-lookup"><span data-stu-id="44582-139">If you use a role other than **Information technology manager**, make sure that the role is assigned the following privileges:</span></span>

-   <span data-ttu-id="44582-140">Visa fel för elektroniska signaturer</span><span class="sxs-lookup"><span data-stu-id="44582-140">View electronic signature failures</span></span>
-   <span data-ttu-id="44582-141">Visa databaslogg</span><span class="sxs-lookup"><span data-stu-id="44582-141">View database log</span></span>

## <a name="signing-documents-electronically"></a><span data-ttu-id="44582-142">Signera dokument elektroniskt</span><span class="sxs-lookup"><span data-stu-id="44582-142">Signing documents electronically</span></span>
### <a name="get-a-certificate"></a><span data-ttu-id="44582-143">Hämta ett certifikat</span><span class="sxs-lookup"><span data-stu-id="44582-143">Get a certificate</span></span>

<span data-ttu-id="44582-144">Innan du signerar dokument elektroniskt i Finance and Operations måste du begära ett certifikat.</span><span class="sxs-lookup"><span data-stu-id="44582-144">Before you sign documents electronically in Finance and Operations, you must request a certificate.</span></span> 

<span data-ttu-id="44582-145">**Obs!** Finance and Operations använder Microsoft SQL Server-funktioner för att skapa certifikat och aktivera elektronisk signering.</span><span class="sxs-lookup"><span data-stu-id="44582-145">**Note:** Finance and Operations uses Microsoft SQL Server features to create certificates and enable electronic signing.</span></span> <span data-ttu-id="44582-146">Ingen annan infrastruktur för certifikat eller offentliga nycklar (PKI) krävs.</span><span class="sxs-lookup"><span data-stu-id="44582-146">No additional certificate or public key infrastructure (PKI) is required.</span></span> 

<span data-ttu-id="44582-147">När du begär ett certifikat skapas en offentlig och en privat nyckel för dig i Finance and Operations-databasen.</span><span class="sxs-lookup"><span data-stu-id="44582-147">When you request a certificate, a public key and a private key are created for you in the Finance and Operations database.</span></span> <span data-ttu-id="44582-148">Den privata nyckeln är krypterad med hjälp av ett lösenord som bara du känner till.</span><span class="sxs-lookup"><span data-stu-id="44582-148">The private key is encrypted by using a password that is known only to you.</span></span> <span data-ttu-id="44582-149">När du signerar ett dokument elektroniskt, verifieras din identitet när du anger lösenordet.</span><span class="sxs-lookup"><span data-stu-id="44582-149">When you sign a document electronically, your identity is verified when you enter the password.</span></span> 

<span data-ttu-id="44582-150">Om du vill begära ett certifikat, gå till sidan **Alternativ** och sedan till fliken **Konton** och klicka på **Hämta certifikat**.</span><span class="sxs-lookup"><span data-stu-id="44582-150">To request a certificate, on the **Options** page, on the **Accounts** tab, click **Get certificate**.</span></span> 

<span data-ttu-id="44582-151">Ange och bekräfta det lösenord du ska använda för signeringen.</span><span class="sxs-lookup"><span data-stu-id="44582-151">You must enter and confirm the password that you will use for signing.</span></span> <span data-ttu-id="44582-152">Lösenordet används för att skydda din privata nyckel och godkänna användningen av certifikatet.</span><span class="sxs-lookup"><span data-stu-id="44582-152">The password is used to protect your private key and authorize the use of your certificate.</span></span> <span data-ttu-id="44582-153">Detta lösenord lagras inte i databasen och är inte tillgängligt för någon annan, inte ens Finance and Operations-administratören.</span><span class="sxs-lookup"><span data-stu-id="44582-153">This password isn't stored in the database, and it isn't available to anyone else, not even to the Finance and Operations administrator.</span></span> 

<span data-ttu-id="44582-154">Om du har glömt lösenordet som är kopplat till ditt certifikat måste certifikatet återställas.</span><span class="sxs-lookup"><span data-stu-id="44582-154">If you forget the password that is connected with your certificate, that certificate must be reset.</span></span> <span data-ttu-id="44582-155">När du återställer certifikatet påverkas inte dokument som du signerat med hjälp av det föregående certifikatet.</span><span class="sxs-lookup"><span data-stu-id="44582-155">If you reset the certificate, you don't affect documents that you signed by using the previous certificate.</span></span> <span data-ttu-id="44582-156">Om du vill återställa ett certifikat, gå till sidan **Alternativ** och klicka på **Återställ certifikat**.</span><span class="sxs-lookup"><span data-stu-id="44582-156">To reset the certificate, on the **Options** page, click **Reset certificate**.</span></span>

### <a name="sign-a-document-electronically"></a><span data-ttu-id="44582-157">Underteckna ett dokument elektroniskt</span><span class="sxs-lookup"><span data-stu-id="44582-157">Sign a document electronically</span></span>

<span data-ttu-id="44582-158">Sidan **Signera dokument** visas när du gör en ändring som kräver en elektronisk signatur.</span><span class="sxs-lookup"><span data-stu-id="44582-158">The **Sign document** page is displayed when you make a change that requires an electronic signature.</span></span>

1.  <span data-ttu-id="44582-159">Gå till sidan **Signera dokument** och klicka på fliken **Dokument** om du vill granska ändringarna i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="44582-159">On the **Sign document** page, click the **Document** tab to review the changes to the document.</span></span>
2.  <span data-ttu-id="44582-160">Välj en orsakskod på fliken **Signatur**.</span><span class="sxs-lookup"><span data-stu-id="44582-160">On the **Signature** tab, select a reason code.</span></span>
3.  <span data-ttu-id="44582-161">Skriv in en kommentar om en kommentar är obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="44582-161">Enter a comment, if a comment is required.</span></span>
4.  <span data-ttu-id="44582-162">Om ditt användar-ID inte visas i fältet **Undertecknare** ska du välja det i listan.</span><span class="sxs-lookup"><span data-stu-id="44582-162">If your user ID doesn't appear in the **Signer** field, select it in the list.</span></span>
5.  <span data-ttu-id="44582-163">Ange din plats, om denna information är obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="44582-163">Enter your location, if this information is required.</span></span>
6.  <span data-ttu-id="44582-164">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="44582-164">Click **OK**.</span></span>

### <a name="sign-for-another-users-changes"></a><span data-ttu-id="44582-165">Underteckna en annan användares ändringar</span><span class="sxs-lookup"><span data-stu-id="44582-165">Sign for another user's changes</span></span>

<span data-ttu-id="44582-166">Ibland kanske du vill att en användare ska signera en annan användares ändringar.</span><span class="sxs-lookup"><span data-stu-id="44582-166">Occasionally, you might want a user to sign for another user's changes.</span></span> <span data-ttu-id="44582-167">Exempelvis kan det vara nödvändigt för en arbetsledare att signera ändringar som en medarbetare gör i en strukturlista.</span><span class="sxs-lookup"><span data-stu-id="44582-167">For example, a supervisor might be required to sign for changes that an employee makes to a bill of materials (BOM).</span></span> <span data-ttu-id="44582-168">Använd denna procedur när du vill ange en Finance and Operations-användare som undertecknare för en annan användare.</span><span class="sxs-lookup"><span data-stu-id="44582-168">Use this procedure to designate a Finance and Operations user as a signer for another user.</span></span> 

<span data-ttu-id="44582-169">**Obs!** När en användare signerar en annan användares ändringar måste signaturen tillhandahållas på arbetsstationen för den användare som införde ändringen.</span><span class="sxs-lookup"><span data-stu-id="44582-169">**Note:** When one user signs for another user's change, the signature must be provided at the workstation of the user who made the change.</span></span> <span data-ttu-id="44582-170">Användaren kan inte spara ändringen förrän signaturen har tillhandahållits.</span><span class="sxs-lookup"><span data-stu-id="44582-170">The user can't save the change until the signature has been provided.</span></span> 

<span data-ttu-id="44582-171">Följ dessa steg om du vill utse godkännare.</span><span class="sxs-lookup"><span data-stu-id="44582-171">To designate approvers, follow these steps.</span></span>

1.  <span data-ttu-id="44582-172">Gå till sidan **Alternativ** och sedan till fliken **Konton** och klicka på **Utse godkännare**.</span><span class="sxs-lookup"><span data-stu-id="44582-172">On the **Options** page, on the **Accounts** tab, click **Designate approver**.</span></span>
2.  <span data-ttu-id="44582-173">Välj ID för den användare som ska signera för andra användarens ändringar i fältet **Godkänn användar-ID**.</span><span class="sxs-lookup"><span data-stu-id="44582-173">In the **Approver user ID** field, select the ID of the user who must sign for another user's changes.</span></span>
3.  <span data-ttu-id="44582-174">Välj ID för den användare vars ändringar måste signeras i fältet **Signera för användar-ID**.</span><span class="sxs-lookup"><span data-stu-id="44582-174">In the **Sign for user ID** field, select the ID of the user whose changes must be signed for.</span></span>





