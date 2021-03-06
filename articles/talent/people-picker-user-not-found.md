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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462635"
---
# <a name="user-not-found-in-people-picker-in-attract-or-onboard"></a>Användaren hittades inte i personväljaren i Attract eller Onboard

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Utleverans

Vissa giltiga användare i Microsoft Azure Active Directory (Azure AD) för innehavare visas inte när du söker efter namn i personväljaren i Dynamics 365 Talent: Attract eller Dynamics 365 Talent: Onboard.

## <a name="cause"></a>Orsak

Vissa användartyper stöds inte i Attract och Onboard. Kontrollera att användaren inte är en Azure AD Business to Business (B2B) gästanvändare. ”Användartyp”-information finns i bladet Azure Active Directory på Azure portalen.

Mer information om Azure B2B finns i [vad är gästanvändaråtkomst i Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).

För icke-B2B-användare finns vissa användare som kanske har en ofullständig ”användartyp”-egenskapen för objektet **användare**. Detta kan verifieras och fästas med Azure AD Powershell-modulen. Mer information finns i [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]