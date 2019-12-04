---
title: Användaren hittades inte i personväljaren i Attract eller Onboard
description: Det här avsnittet beskriver hur användare i företagets innehavare inte visas i personväljaren i Dynamics 365 Talent - Attract eller Onboard-program.
author: andreabichsel
manager: AnnBe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a6d916f87ca30aa7405a51841e56ab31bbe31ac8
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832614"
---
# <a name="user-not-found-in-people-picker-in-attract-or-onboard"></a><span data-ttu-id="71194-103">Användaren hittades inte i personväljaren i Attract eller Onboard</span><span class="sxs-lookup"><span data-stu-id="71194-103">User not found in People Picker in Attract or Onboard</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="71194-104">Utleverans</span><span class="sxs-lookup"><span data-stu-id="71194-104">Issue</span></span>

<span data-ttu-id="71194-105">Vissa giltiga användare i Microsoft Azure Active Directory (Azure AD) för innehavare visas inte när du söker efter namn i personväljaren i Dynamics 365 Talent: Attract eller Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="71194-105">Certain valid users in Microsoft Azure Active Directory (Azure AD) for the tenant do not appear when searching for the name in the People Picker in Dynamics 365 Talent: Attract or Dynamics 365 Talent: Onboard.</span></span>

## <a name="cause"></a><span data-ttu-id="71194-106">Orsak</span><span class="sxs-lookup"><span data-stu-id="71194-106">Cause</span></span>

<span data-ttu-id="71194-107">Vissa användartyper stöds inte i Attract och Onboard.</span><span class="sxs-lookup"><span data-stu-id="71194-107">Certain user types are not currently supported in Attract and Onboard.</span></span> <span data-ttu-id="71194-108">Kontrollera att användaren inte är en Azure AD Business to Business (B2B) gästanvändare.</span><span class="sxs-lookup"><span data-stu-id="71194-108">Verify that the user is not an Azure AD Business to Business (B2B) guest user.</span></span> <span data-ttu-id="71194-109">”Användartyp”-information finns i bladet Azure Active Directory på Azure portalen.</span><span class="sxs-lookup"><span data-stu-id="71194-109">"User Type" information can be found in the Azure Active Directory blade on the Azure portal.</span></span>

<span data-ttu-id="71194-110">Mer information om Azure B2B finns i [vad är gästanvändaråtkomst i Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="71194-110">For more information about Azure B2B, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span>

<span data-ttu-id="71194-111">För icke-B2B-användare finns vissa användare som kanske har en ofullständig ”användartyp”-egenskapen för objektet **användare**.</span><span class="sxs-lookup"><span data-stu-id="71194-111">For non-B2B users, there are certain users who may have an incomplete "User Type" property on the **User** object.</span></span> <span data-ttu-id="71194-112">Detta kan verifieras och fästas med Azure AD Powershell-modulen.</span><span class="sxs-lookup"><span data-stu-id="71194-112">This can be verified and fixed using the Azure AD Powershell module.</span></span> <span data-ttu-id="71194-113">Mer information finns i [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="71194-113">For more information, see [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span></span>

## <a name="resolution"></a><span data-ttu-id="71194-114">Upplösning</span><span class="sxs-lookup"><span data-stu-id="71194-114">Resolution</span></span>

<span data-ttu-id="71194-115">Slutför följande steg för att lösa problemet måste du ha ”globala” administratörsrättigheter till Azure Active Directory innehavare eller behörigheter för **User.ReadWrite.All**.</span><span class="sxs-lookup"><span data-stu-id="71194-115">To complete the following steps to resolve the issue, you will need to have "Global Administrator" permissions on the Azure Active Directory tenant or permissions for **User.ReadWrite.All**.</span></span>

<span data-ttu-id="71194-116">Verifiera ”användartyp” för den aktuella användaren.</span><span class="sxs-lookup"><span data-stu-id="71194-116">To verify the "User Type" for the affected user.</span></span>

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
<span data-ttu-id="71194-117">Kommandot returnerar följande information.</span><span class="sxs-lookup"><span data-stu-id="71194-117">The command returns the following information.</span></span>
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
<span data-ttu-id="71194-118">Observera egenskapen **UserType** för användaren.</span><span class="sxs-lookup"><span data-stu-id="71194-118">Note the **UserType** property on the user.</span></span> <span data-ttu-id="71194-119">Om **UserType** är tom, till exempel inte ”medlem” eller ”gäst” uppdaterar du **UserType** med följande kommando.</span><span class="sxs-lookup"><span data-stu-id="71194-119">If the **UserType** is blank, for example not "Member" or "Guest", update the **UserType** using the following command.</span></span>

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
