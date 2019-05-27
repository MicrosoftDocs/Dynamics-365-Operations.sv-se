---
title: Användaren hittades inte i personväljaren i Attract eller Onboard
description: Det här avsnittet beskriver hur användare i företagets innehavare inte visas i personväljaren i Dynamics 365 for Talent Attract eller Onboard-program.
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
ms.openlocfilehash: d5a2c61fc21578d1db4c1bf0c3dfaf0c7a93298c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519112"
---
# <a name="azure-active-directory-users-not-found-in-people-picker"></a>Azure Active Directory-användare som inte finns i personväljaren

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Utleverans

Vissa giltiga användare i Microsoft Azure Active Directory (Azure AD) för innehavare visas inte när du söker efter namn i personväljaren i Dynamics 365 for Talent Attract eller Onboard-program.

## <a name="cause"></a>Orsak

Vissa användartyper stöds inte i Attract och Onboard-program. Kontrollera att användaren inte är en Azure AD Business to Business (B2B) gästanvändare. ”Användartyp”-information finns i bladet Azure Active Directory på Azure portalen.

Mer information om Azure B2B finns i [vad är gästanvändaråtkomst i Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).

För icke-B2B-användare finns vissa användare som kanske har en ofullständig ”användartyp”-egenskapen för objektet **användare**. Detta kan verifieras och fästas med Azure AD Powershell-modulen. Mer information finns i [Azure AD](https://docs.microsoft.com/en-us/powershell/module/azuread/?view=azureadps-2.0).

## <a name="resolution"></a>Upplösning

Slutför följande steg för att lösa problemet måste du ha ”globala” administratörsrättigheter till Azure Active Directory innehavare eller behörigheter för **User.ReadWrite.All**.

Verifiera ”användartyp” för den aktuella användaren.

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
Kommandot returnerar följande information.
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
Observera egenskapen **UserType** för användaren. Om **UserType** är tom, till exempel inte ”medlem” eller ”gäst” uppdaterar du **UserType** med följande kommando.

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
