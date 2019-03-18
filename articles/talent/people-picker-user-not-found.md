---
title: Användaren hittades inte i personväljaren i Attract eller Onboard
description: Det här avsnittet beskriver hur användare i företagets innehavare inte visas i personväljaren i Dynamics 365 for Talent Attract eller Onboard-program.
author: ChrisChua
manager: AnnBe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: chrichua
ms.search.validFrom: 2019-01-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2d4a74ee2cc65153c1f9fdc1b42c2fc440d188d6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "306324"
---
# <a name="azure-active-directory-users-not-found-in-people-picker"></a><span data-ttu-id="4e85e-103">Azure Active Directory-användare som inte finns i personväljaren</span><span class="sxs-lookup"><span data-stu-id="4e85e-103">Azure Active Directory users not found in People Picker</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="4e85e-104">Utleverans</span><span class="sxs-lookup"><span data-stu-id="4e85e-104">Issue</span></span>

<span data-ttu-id="4e85e-105">Vissa giltiga användare i Microsoft Azure Active Directory (Azure AD) för innehavare visas inte när du söker efter namn i personväljaren i Dynamics 365 for Talent Attract eller Onboard-program.</span><span class="sxs-lookup"><span data-stu-id="4e85e-105">Certain valid users in Microsoft Azure Active Directory (Azure AD) for the tenant do not appear when searching for the name in the People Picker in the Dynamics 365 for Talent Attract or Onboard applications.</span></span>

## <a name="cause"></a><span data-ttu-id="4e85e-106">Orsak</span><span class="sxs-lookup"><span data-stu-id="4e85e-106">Cause</span></span>

<span data-ttu-id="4e85e-107">Vissa användartyper stöds inte i Attract och Onboard-program.</span><span class="sxs-lookup"><span data-stu-id="4e85e-107">Certain user types are not currently supported in the Attract and Onboard applications.</span></span> <span data-ttu-id="4e85e-108">Kontrollera att användaren inte är en Azure AD Business to Business (B2B) gästanvändare.</span><span class="sxs-lookup"><span data-stu-id="4e85e-108">Verify that the user is not an Azure AD Business to Business (B2B) guest user.</span></span> <span data-ttu-id="4e85e-109">”Användartyp”-information finns i bladet Azure Active Directory på Azure portalen.</span><span class="sxs-lookup"><span data-stu-id="4e85e-109">"User Type" information can be found in the Azure Active Directory blade on the Azure portal.</span></span>

<span data-ttu-id="4e85e-110">Mer information om Azure B2B finns i [vad är gästanvändaråtkomst i Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="4e85e-110">For more information about Azure B2B, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).</span></span>

<span data-ttu-id="4e85e-111">För icke-B2B-användare finns vissa användare som kanske har en ofullständig ”användartyp”-egenskapen för objektet **användare**.</span><span class="sxs-lookup"><span data-stu-id="4e85e-111">For non-B2B users, there are certain users who may have an incomplete "User Type" property on the **User** object.</span></span> <span data-ttu-id="4e85e-112">Detta kan verifieras och fästas med Azure AD Powershell-modulen.</span><span class="sxs-lookup"><span data-stu-id="4e85e-112">This can be verified and fixed using the Azure AD Powershell module.</span></span> <span data-ttu-id="4e85e-113">Mer information finns i [Azure AD](https://docs.microsoft.com/en-us/powershell/module/azuread/?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="4e85e-113">For more information, see [Azure AD](https://docs.microsoft.com/en-us/powershell/module/azuread/?view=azureadps-2.0).</span></span>

## <a name="resolution"></a><span data-ttu-id="4e85e-114">Upplösning</span><span class="sxs-lookup"><span data-stu-id="4e85e-114">Resolution</span></span>

<span data-ttu-id="4e85e-115">Slutför följande steg för att lösa problemet måste du ha ”globala” administratörsrättigheter till Azure Active Directory innehavare eller behörigheter för **User.ReadWrite.All**.</span><span class="sxs-lookup"><span data-stu-id="4e85e-115">To complete the following steps to resolve the issue, you will need to have "Global Administrator" permissions on the Azure Active Directory tenant or permissions for **User.ReadWrite.All**.</span></span>

<span data-ttu-id="4e85e-116">Verifiera ”användartyp” för den aktuella användaren.</span><span class="sxs-lookup"><span data-stu-id="4e85e-116">To verify the "User Type" for the affected user.</span></span>

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
<span data-ttu-id="4e85e-117">Kommandot returnerar följande information.</span><span class="sxs-lookup"><span data-stu-id="4e85e-117">The command returns the following information.</span></span>
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
<span data-ttu-id="4e85e-118">Observera egenskapen **UserType** för användaren.</span><span class="sxs-lookup"><span data-stu-id="4e85e-118">Note the **UserType** property on the user.</span></span> <span data-ttu-id="4e85e-119">Om **UserType** är tom, till exempel inte ”medlem” eller ”gäst” uppdaterar du **UserType** med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="4e85e-119">If the **UserType** is blank, for example not "Member" or "Guest", update the **UserType** using the following command.</span></span>

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```