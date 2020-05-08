---
title: Aktivera Azure Active Directory-autentisering för kassainloggning
description: I det här avsnittet beskrivs hur du konfigurerar inloggnings upplevelsen för Microsoft Dynamics 365 Commerce kassa (POS) så att den använder Azure Active Directory-autentisering.
author: boycezhu
manager: annbe
ms.date: 03/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: dfc49585434383385b6b993893d93b95ef888384
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "3248950"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a>Aktivera Azure Active Directory-autentisering för kassainloggning
[!include [banner](includes/banner.md)]


Många kunder som använder Microsoft Dynamics 365 Commerce använder också andra Microsoft Cloud Service och de kan använda Azure Active Directory (Azure AD) för att hantera användarbehörigheter för dessa tjänster. I dessa fall kanske kunderna vill använda samma Azure AD-konto i olika program. I det här avsnittet beskrivs hur du konfigurerar inloggnings upplevelsen för Commerce-kassa (POS) så att den använder Azure AD-autentisering.

## <a name="configure-azure-ad-authentication"></a>Konfigurera Azure AD-autentisering

Om du vill göra Azure AD tillgänglig som autentiseringsmetod för kassainloggning för en butik måste du konfigurera inställningarna för butikens funktionsprofil och sedan tillämpa dessa inställningar på kassaklienter.

Följ dessa steg för att konfigurera en ny funktionsprofil.

1. Gå till **Butik och handel** \> **Kanalinställningar** \> **Kassainställningar** \> **Kassaprofiler** \> **Funktionsprofiler**.
1. Välj den funktionsprofil som du vill ändra.
1. På snabbfliken **funktioner** i avsnittet **kassapersonalinloggning**, ändra värdet i fältet **Autentiseringsmetod för inloggning** från **Personal-ID och lösenord** till **Azure Active Directory**.

Som standard använder alla funktionsprofiler **Personal-ID och lösenord** som autentiseringsmetod för kassan. Därför måste du ändra värdet för **Autentiseringsmetod för inloggning** om du vill använda Azure AD. Alla butiker som är kopplade till den valda funktionsprofilen påverkas av den här ändringen.

För att tillämpa inställningarna till kassaklienter, följ dessa steg instruktioner.

1. Gå till **Butik och handel** \> **Butik och handel-IT** \> **Distributionsschema**.
1. Kör distributionsschemat **1070** (**Kanalkonfiguration**).

> [!NOTE]
> Azure AD autentisering kräver en Internetanslutning. Det fungerar inte när kassan är i offline-läge.

## <a name="associate-an-azure-ad-account-with-a-worker"></a>Associera ett Azure AD-konto med en arbetare

Innan en butiksarbetare kan använda ett Azure AD-konto för att logga in på kassaprogrammet måste Azure AD-kontot vara kopplat till den personen.

Om du vill associera ett Azure AD-konto med en arbetare följer du stegen nedan.

1. Gå till **Retail och Commerce** \> **Anställda** \> **Arbetare**.
1. Öppna informationssidan för en arbetare.
1. I åtgärdsfönstret, på fliken **Commerce** i gruppen **Extern identitet** markerar du **Associera befintlig identitet**.
1. I dialogrutan **Använd befintlig extern identitet**, välj **Sök med e-post**, ange en Azure AD e-postadress och välj **Sök**.
1. Markera Azure AD-kontot som returneras och välj sedan **OK**.

Fälten **Alias**, **UPN** och **Extern underidentifierare** på fliken **Commerce** på arbetarens detaljsida fylls i.

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in utökad inloggningsfunktion för MPOS och molnbaserad kassa](extended-logon.md)

[Skapa en Retail-funktionsprofil](retail-functionality-profile.md)

[ Konfigurera en arbetare](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)